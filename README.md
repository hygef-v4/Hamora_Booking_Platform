# Hamora Booking Platform

[![Demo](https://img.shields.io/badge/Demo-Live-brightgreen)](https://hamora.live)
[![Java](https://img.shields.io/badge/Java-17-orange)](https://www.oracle.com/java/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.4.5-green)](https://spring.io/projects/spring-boot)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

Hamora is a full-stack hotel booking platform built with Spring Boot, designed for real-world marketplace flows across customers, hosts, moderators, and admins. It delivers end-to-end booking, payments, communication, and operations dashboards in one system.

Live demo: https://hamora.live

## Why this project stands out

- Multi-role product surface with tailored dashboards and permissions.
- End-to-end booking pipeline: search, booking, payment, and post-stay reviews.
- Real-time engagement: WebSocket chat and in-app notifications.
- Production-style integrations: VNPay payments, Cloudinary media, OAuth2 login, email.
- Dockerized environment with SQL Server and Redis.

## Core features

- Customer discovery: search by location/date/guests, filters by price, amenities, and rating.
- Hotel operations: host onboarding, hotel and room management, media uploads, review handling.
- Payments and promotions: VNPay integration, coupons, refund workflows.
- Communication: live chat, notifications, contact/report tools, Dialogflow chatbot.
- Analytics: role-specific dashboards and revenue/booking insights.

## Tech stack

- Backend: Java 17, Spring Boot 3.4.5, Spring Security, JDBC, Thymeleaf, WebSocket
- Data: Microsoft SQL Server, Redis
- Integrations: Cloudinary, VNPay, OAuth2, Spring Mail, Dialogflow
- DevOps: Maven, Docker, SonarQube

## Project structure

```
HotelBookingSystem/
├── src/main/java/org/swp391/hotelbookingsystem/
│   ├── config/
│   ├── controller/
│   ├── service/
│   ├── repository/
│   ├── model/
│   ├── dto/
│   ├── handler/
│   └── filter/
├── src/main/resources/
│   ├── templates/
│   ├── static/
│   └── application.properties
└── pom.xml
```

## Run locally

Prerequisites: Java 17+, Maven 3.6+, SQL Server, Redis (optional)

1) Clone and enter the app
```bash
git clone https://github.com/hygef-v4/Hamora_Booking_Platform.git
cd Hamora_Booking_Platform/HotelBookingSystem
```

2) Configure database in `src/main/resources/application.properties`
```properties
spring.datasource.url=jdbc:sqlserver://localhost:1433;databaseName=HotelBooking
spring.datasource.username=your_username
spring.datasource.password=your_password
```

3) Configure external services (optional but recommended)
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

4) Start the application
```bash
mvn spring-boot:run
```

5) Open
- Local: http://localhost:8080
- Demo: https://hamora.live

## Run with Docker

```bash
docker build -t hamora-hotel-booking .
docker-compose up -d
```

## Team

This project was built as part of the SWP391 course by:

- Khuat Quang Hung
- Dao Chi Cuong
- Vo Chien Thang
- Vu Hai Nam
- Vo Minh Tai

## Contact

- Demo: https://hamora.live
- Email: hungsct1702@gmail.com
- GitHub: https://github.com/hygef-v4/Hamora_Booking_Platform
