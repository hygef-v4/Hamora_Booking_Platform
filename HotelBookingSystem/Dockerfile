# ============================================================
# Stage 1: BUILD
# Dùng JDK + Maven để compile và đóng gói JAR
# Image này sẽ KHÔNG có trong final image
# ============================================================
FROM eclipse-temurin:17-jdk-jammy AS builder

WORKDIR /app

# Copy Maven wrapper trước để cache layer dependencies
COPY mvnw mvnw.cmd pom.xml ./
COPY .mvn .mvn

# Fix line endings cho mvnw (cần thiết khi build trên Windows)
RUN sed -i 's/\r$//' mvnw && chmod +x mvnw

# Download dependencies (layer này được cache nếu pom.xml không đổi)
RUN ./mvnw dependency:go-offline -B

# Copy source code và build
COPY src src
RUN ./mvnw clean package -DskipTests -B

# Giải nén Spring Boot layered JAR để tối ưu Docker layers
RUN java -Djarmode=layertools -jar target/HotelBookingSystem-0.0.1-SNAPSHOT.jar extract --destination target/extracted

# ============================================================
# Stage 2: RUNTIME
# Chỉ dùng JRE Alpine (nhỏ hơn ~3x so với JDK)
# Final image chỉ chứa JRE + app layers, không có Maven/JDK
# ============================================================
FROM eclipse-temurin:17-jre-alpine AS runtime

WORKDIR /app

# Tạo user không phải root để bảo mật
RUN addgroup -S appgroup && adduser -S appuser -G appgroup
USER appuser

# Copy các layers theo thứ tự từ ít thay đổi nhất → thường xuyên nhất
# Giúp Docker cache hiệu quả hơn khi chỉ code thay đổi
COPY --from=builder /app/target/extracted/dependencies/ ./
COPY --from=builder /app/target/extracted/spring-boot-loader/ ./
COPY --from=builder /app/target/extracted/snapshot-dependencies/ ./
COPY --from=builder /app/target/extracted/application/ ./

EXPOSE 8386

# Dùng Spring Boot Launcher thay vì gọi jar trực tiếp
ENTRYPOINT ["java", "org.springframework.boot.loader.launch.JarLauncher"]