# Hamora Booking Platform

[![Demo](https://img.shields.io/badge/Demo-Live-brightgreen)](https://hamora-booking-platform.onrender.com)
[![Java](https://img.shields.io/badge/Java-17-orange)](https://www.oracle.com/java/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.4.5-green)](https://spring.io/projects/spring-boot)
[![Docker](https://img.shields.io/badge/Docker-Ready-blue)](https://www.docker.com/)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

Hamora is a full-stack hotel booking platform built with Spring Boot, designed for real-world marketplace flows across customers, hosts, moderators, and admins. It delivers end-to-end booking, payments, communication, and operations dashboards in one system.

🌐 **Live Demo:** [https://hamora-booking-platform.onrender.com](https://hamora-booking-platform.onrender.com)

---

## Why this project stands out

- Multi-role product surface with tailored dashboards and permissions.
- End-to-end booking pipeline: search, booking, payment, and post-stay reviews.
- Real-time engagement: WebSocket chat and in-app notifications.
- Production-style integrations: VNPay payments, Cloudinary media, OAuth2 login, email.
- Dockerized and deployed on Render with Azure SQL Database.

---

## Core Features

| Feature | Details |
|---------|---------|
| 🔍 **Search & Discovery** | Filter by location, date, guests, price, amenities, rating |
| 🏨 **Hotel Management** | Host onboarding, room setup, media uploads, review handling |
| 💳 **Payments** | VNPay integration, coupon/promotion system, refund workflows |
| 💬 **Communication** | Live WebSocket chat, in-app notifications, Dialogflow chatbot |
| 📊 **Analytics** | Role-specific dashboards with revenue & booking insights |
| 🔐 **Authentication** | Google OAuth2, Spring Security, role-based access control |

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| **Backend** | Java 17, Spring Boot 3.4.5, Spring Security, Spring WebSocket |
| **View** | Thymeleaf, HTML/CSS/JS |
| **Database** | Microsoft SQL Server (Azure SQL Database) |
| **Storage** | Cloudinary |
| **Payments** | VNPay |
| **Auth** | Spring OAuth2 Client (Google) |
| **Email** | Spring Mail (Gmail SMTP) |
| **Chatbot** | Dialogflow |
| **DevOps** | Maven, Docker, Render, SonarQube |

---

## Project Structure

```
HotelBookingSystem/
├── src/main/java/org/swp391/hotelbookingsystem/
│   ├── config/           # Security, OAuth2, WebSocket, Cloudinary config
│   ├── controller/       # MVC Controllers & REST endpoints
│   ├── service/          # Business logic layer
│   ├── repository/       # Data access layer (JDBC)
│   ├── model/            # Entity / domain models
│   ├── dto/              # Data transfer objects
│   ├── handler/          # Custom authentication handlers
│   └── filter/           # Security filters
├── src/main/resources/
│   ├── templates/        # Thymeleaf HTML templates
│   ├── static/           # CSS, JS, images
│   └── application.properties
├── Dockerfile
├── docker-compose.yml
└── pom.xml
```

---

## Run Locally

**Prerequisites:** Java 17+, Maven 3.6+

### 1. Clone the repository

```bash
git clone https://github.com/hygef-v4/Hamora_Booking_Platform.git
cd Hamora_Booking_Platform/HotelBookingSystem
```

### 2. Configure environment variables

Copy the example env file and fill in your values:

```bash
cp .env.example .env
```

```env
SERVER_PORT=8386
APP_BASE_URL=http://localhost:8386

DB_URL=jdbc:sqlserver://localhost:1433;databaseName=RoomBooking;encrypt=false;trustServerCertificate=true
DB_USERNAME=sa
DB_PASSWORD=your_password

GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret

MAIL_USERNAME=your_email@gmail.com
MAIL_PASSWORD=your_app_password

CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret
```

### 3. Run the application

```bash
./mvnw spring-boot:run
```

Open: [http://localhost:8386](http://localhost:8386)

---

## Run with Docker

```bash
docker compose up --build
```

The app will be available at [http://localhost:8386](http://localhost:8386)

> The app connects to Azure SQL Database via `DB_URL` — no local SQL Server container required.

---

## Deployment

The application is deployed on **Render** using Docker:

- **Platform:** [Render](https://render.com)
- **Database:** Azure SQL Database (Microsoft Azure)
- **Storage:** Cloudinary
- **Live URL:** [https://hamora-booking-platform.onrender.com](https://hamora-booking-platform.onrender.com)

---

## Team

This project was built as part of the SWP391 course:

| Name | GitHub |
|------|--------|
| Khuat Quang Hung | [@hygef-v4](https://github.com/hygef-v4) |
| Dao Chi Cuong | [@chi-cuongg](https://github.com/chi-cuongg) |
| Vo Chien Thang | [@ThangVoChien](https://github.com/ThangVoChien) |
| Vu Hai Nam | [@HNam1315](https://github.com/HNam1315) |
| Vo Minh Tai | [@tai30052005](https://github.com/tai30052005) |

---

## Contact

- 🌐 Demo: [https://hamora-booking-platform.onrender.com](https://hamora-booking-platform.onrender.com)
- 📧 Email: hungsct1702@gmail.com
- 🐙 GitHub: [https://github.com/hygef-v4/Hamora_Booking_Platform](https://github.com/hygef-v4/Hamora_Booking_Platform)
