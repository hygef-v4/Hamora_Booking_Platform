# 🏨 Hamora Booking Platform - Hệ thống đặt phòng khách sạn

[![Demo](https://img.shields.io/badge/Demo-Live-brightgreen)](https://hamora.live)
[![Java](https://img.shields.io/badge/Java-17-orange)](https://www.oracle.com/java/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.4.5-green)](https://spring.io/projects/spring-boot)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

## 🌟 Giới thiệu

**Hamora Booking Platform** là một hệ thống đặt phòng khách sạn toàn diện được phát triển bằng Spring Boot trong khuôn khổ môn SWP391, cung cấp trải nghiệm đặt phòng trực tuyến hiện đại và tiện lợi cho cả khách hàng và chủ khách sạn.

🔗 **Demo trực tiếp**: [hamora.live](https://hamora.live)

## ✨ Tính năng chính

### 👥 Đa vai trò người dùng
- **Khách hàng**: Tìm kiếm, đặt phòng, quản lý booking
- **Chủ khách sạn (Host)**: Quản lý khách sạn, phòng, đơn đặt
- **Moderator**: Kiểm duyệt nội dung, quản lý báo cáo
- **Admin**: Quản trị toàn hệ thống

### 🏨 Quản lý khách sạn
- Đăng ký và quản lý thông tin khách sạn
- Upload hình ảnh với Cloudinary
- Quản lý phòng và tiện nghi
- Theo dõi đánh giá và phản hồi khách hàng

### 🔍 Tìm kiếm và đặt phòng
- Tìm kiếm theo địa điểm, ngày, số khách
- Lọc theo giá, tiện nghi, đánh giá
- So sánh khách sạn
- Đặt phòng với nhiều tùy chọn thanh toán

### 💳 Thanh toán tích hợp
- Tích hợp VNPay cho thanh toán trực tuyến
- Hỗ trợ mã giảm giá (Coupon)
- Quản lý hoàn tiền theo chính sách

### 💬 Giao tiếp và hỗ trợ
- Chat realtime giữa khách hàng và host
- Hệ thống thông báo tức thời
- Chatbot tích hợp Dialogflow
- Liên hệ và báo cáo

### 📊 Dashboard và báo cáo
- Dashboard cho từng vai trò người dùng
- Thống kê doanh thu, booking
- Quản lý đánh giá và phản hồi
- Báo cáo chi tiết

## 🛠️ Công nghệ sử dụng

### Backend
- **Java 17** - Ngôn ngữ lập trình chính
- **Spring Boot 3.4.5** - Framework backend
- **Spring Security** - Bảo mật và xác thực
- **JDBC** - Quản lý database và kết nối trực tiếp
- **Thymeleaf** - Template engine
- **WebSocket** - Chat realtime

### Database
- **Microsoft SQL Server** - Cơ sở dữ liệu chính
- **Redis** - Cache và session storage

### Tích hợp bên ngoài
- **Cloudinary** - Quản lý và lưu trữ hình ảnh
- **VNPay** - Cổng thanh toán
- **Spring Mail** - Gửi email
- **OAuth2** - Đăng nhập xã hội
- **Dialogflow** - Chatbot AI

### DevOps
- **Docker** - Containerization
- **Maven** - Build tool
- **SonarQube** - Code quality

## 🚀 Cài đặt và chạy dự án

### Yêu cầu hệ thống
- Java 17+
- Maven 3.6+
- SQL Server
- Redis (optional)

### 1. Clone repository
```bash
git clone https://github.com/hygef-v4/Hamora_Booking_Platform.git
cd Hamora_Booking_Platform/HotelBookingSystem
```

### 2. Cấu hình database
Cập nhật file `src/main/resources/application.properties`:
```properties
spring.datasource.url=jdbc:sqlserver://localhost:1433;databaseName=HotelBooking
spring.datasource.username=your_username
spring.datasource.password=your_password
```

### 3. Cấu hình các service bên ngoài
```properties
# Cloudinary
cloudinary.cloud-name=your_cloud_name
cloudinary.api-key=your_api_key
cloudinary.api-secret=your_api_secret

# VNPay
vnpay.tmn-code=your_tmn_code
vnpay.hash-secret=your_hash_secret

# Email
spring.mail.username=your_email
spring.mail.password=your_password
```

### 4. Chạy ứng dụng
```bash
mvn spring-boot:run
```

### 5. Truy cập ứng dụng
- **Local**: http://localhost:8080
- **Demo**: https://hamora.live

## 🐳 Chạy với Docker

```bash
# Build image
docker build -t hamora-hotel-booking .

# Chạy với docker-compose
docker-compose up -d
```

## 📱 Screenshots

### 🏠 Trang chủ
Giao diện hiện đại với tìm kiếm nhanh và khách sạn nổi bật

### 🔍 Tìm kiếm và lọc
Tìm kiếm theo nhiều tiêu chí với kết quả chi tiết

### 🏨 Chi tiết khách sạn
Thông tin đầy đủ với hình ảnh, tiện nghi và đánh giá

### 💳 Đặt phòng và thanh toán
Quy trình đặt phòng đơn giản với nhiều tùy chọn thanh toán

## 🏗️ Kiến trúc hệ thống

```
HotelBookingSystem/
├── src/main/java/org/swp391/hotelbookingsystem/
│   ├── config/          # Cấu hình Spring
│   ├── controller/      # REST Controllers
│   ├── service/         # Business Logic
│   ├── repository/      # Data Access Layer
│   ├── model/          # Entity Models
│   ├── dto/            # Data Transfer Objects
│   ├── handler/        # Custom Handlers
│   └── filter/         # Security Filters
├── src/main/resources/
│   ├── templates/      # Thymeleaf Templates
│   ├── static/         # CSS, JS, Images
│   └── application.properties
└── pom.xml
```

## 🤝 Đóng góp

Chúng tôi hoan nghênh mọi đóng góp để cải thiện dự án!

1. Fork repository
2. Tạo feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Tạo Pull Request

## 📄 License

Dự án này được phân phối dưới MIT License. Xem file `LICENSE` để biết thêm chi tiết.

## 👨‍💻 Team phát triển

Dự án **Hamora Booking Platform** được phát triển bởi nhóm sinh viên trong khuôn khổ môn SWP391:

- **Khuất Quang Hưng** 
- **Đào Chí Cường** 
- **Võ Chiến Thắng** 
- **Vũ Hải Nam** 
- **Võ Minh Tài** 

## 📞 Liên hệ

- **Demo**: [hamora.live](https://hamora.live)
- **Email**: hungsct1702@gmail.com
- **GitHub**: [https://github.com/hygef-v4/Hamora_Booking_Platform](https://github.com/hygef-v4/Hamora_Booking_Platform)

---

⭐ **Nếu bạn thấy dự án hữu ích, hãy cho chúng tôi một star!** ⭐
