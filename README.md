<h1 align="center">One Piece</h1>
<p align="center"><em>A Scalable Online Auction & Bidding Ecosystem</em></p>

<p align="center"><em>Built with the tools and technologies:</em></p>

<p align="center">
  <img alt="Java" src="https://img.shields.io/badge/Java-ED8B00?logo=openjdk&logoColor=white" />
  <img alt="Spring Boot" src="https://img.shields.io/badge/Spring_Boot-6DB33F?logo=spring-boot&logoColor=white" />
  <img alt="Spring Security" src="https://img.shields.io/badge/Spring_Security-6DB33F?logo=spring-security&logoColor=white" />
  <img alt="Spring Cloud" src="https://img.shields.io/badge/Spring_Cloud-6DB33F?logo=spring&logoColor=white" />
  <img alt="Hibernate" src="https://img.shields.io/badge/Hibernate-59666C?logo=hibernate&logoColor=white" />
  <img alt="React" src="https://img.shields.io/badge/React-61DAFB?logo=react&logoColor=black" />
  <img alt="Vite" src="https://img.shields.io/badge/Vite-646CFF?logo=vite&logoColor=white" />
  <img alt="React Router" src="https://img.shields.io/badge/React_Router-CA4245?logo=react-router&logoColor=white" />
  <img alt="Axios" src="https://img.shields.io/badge/Axios-5A29E4?logo=axios&logoColor=white" />
  <img alt="Node.js" src="https://img.shields.io/badge/Node.js-339933?logo=nodedotjs&logoColor=white" />
  <img alt="Express" src="https://img.shields.io/badge/Express-000000?logo=express&logoColor=white" />
  <img alt="Maven" src="https://img.shields.io/badge/Maven-C71A36?logo=apachemaven&logoColor=white" />
  <img alt="MySQL" src="https://img.shields.io/badge/MySQL-4479A1?logo=mysql&logoColor=white" />
  <img alt="JWT" src="https://img.shields.io/badge/JWT-black?logo=jsonwebtokens&logoColor=white" />
  <img alt="Postman" src="https://img.shields.io/badge/Postman-FF6C37?logo=postman&logoColor=white" />
  <img alt="Lombok" src="https://img.shields.io/badge/Lombok-BC0230?logo=lombok&logoColor=white" />
  <img alt="Tailwind CSS" src="https://img.shields.io/badge/Tailwind_CSS-06B6D4?logo=tailwindcss&logoColor=white" />
  <img alt="shadcn/ui" src="https://img.shields.io/badge/shadcn%2Fui-000000?logo=shadcnui&logoColor=white" />
</p>

---

## Table of Contents

- [Overview](#overview)
- [Project Architecture](#project-architecture)
- [Operational Overview](#operational-overview)
- [Key Features](#key-features)
- [Configuration & Environment Setup](#configuration--environment-setup)
- [Getting Started](#getting-started)
- [Tech Stack](#tech-stack)
- [License](#license)

---

## Overview

**OnePiece** is a comprehensive online auction bidding platform designed to simulate a real-world e-commerce auction bidding environment. This project demonstrates a progressive development journey, evolving from a simple prototype to a complex distributed system.

### Evolution of OnePiece

This project highlights three distinct architectural stages:

- **Mock Server:** Initial prototyping using Node.js/Express to simulate APIs.
- **Monolithic Backend:** A production-ready single application using Spring Boot.
- **Microservices:** A fully scalable architecture using Eureka, API Gateway, and independent services.

---

## Project Architecture

The codebase is organized to reflect the different stages of development:

| Directory | Description |
| :--- | :--- |
| **Frontend** | Built with **React & Vite**. Contains reusable components, role-based pages, and authentication logic. |
| **mockserver** | Prototype backend using **Node.js**. Serves mock JSON data for rapid frontend testing. |
| **Backend** | The **Spring Boot** Monolith. Handles all business logic, persistence, and APIs in one centralized app. |
| **MicroServices** | Scalable ecosystem containing **Eureka Server**, **API Gateway**, and individual domain services (User, Product, Bidding). |

---

## Operational Overview

The platform is designed to facilitate a secure and fair marketplace through three primary operational pillars:

### 1. Unified User Ecosystem
The system supports a flexible account structure. Users start as Buyers but have the capability to upgrade their privileges to become Sellers. The architecture supports **Dual-Role Capabilities**, allowing a single account to seamlessly manage both purchasing activities and product listings within the same session after verification.

### 2. Curated Marketplace & Safety
To ensure platform integrity, the system implements a strict moderation pipeline.
- **Listing Integrity:** All seller submissions undergo an administrative approval process before becoming visible to the public.
- **Fair Play Enforcement:** The bidding engine includes logic to prevent conflict of interest, ensuring sellers cannot artificially inflate the price of their own listings.

### 3. The Auction Lifecycle
The core of the platform is the automated auction engine.
- **Live Bidding:** Products are auctioned within a set time window where competitive bidding occurs.
- **Automated Settlement:** Upon auction conclusion, the highest bidder is automatically identified as the winner.
- **Transaction History:** The system maintains a transparent ledger of payments, ratings, and feedback for completed auctions.

---

## Key Features

- **Real-Time Concurrency & Synchronization**
  The platform is engineered to handle multiple concurrent users seamlessly. Utilizing **React Polling** and optimized backend states, the system has been rigorously tested with simultaneous sessions (Buyers, Sellers, and Admins). Bids, product approvals, and status updates are synchronized in real-time across all connected clients without manual refreshing.

- **Role-Based Access Control (RBAC)**
  Secure, distinct environments for Admins, Buyers, and Sellers with protected route management.

- **Admin Dashboard**
  Centralized control for platform moderation, product approval, and user oversight.

- **Product Inventory Management**
  Tools for sellers to list items, manage images, and track auction statuses.

- **Secure Payment & Reputation System**
  Integrated workflow for post-auction payments and a user rating system to build community trust.

---

## Getting Started

### Prerequisites

Ensure you have the following installed on your machine:

- **Node.js & npm** (for Frontend & Mock Server)
- **Java JDK 8+** (for Backend & Microservices)
- **Maven** (for building Java projects)

### Installation & Running

Choose the architecture you wish to run and follow the specific steps below:

#### 1. Frontend Client
<pre>
cd Frontend
npm install
npm run dev
</pre>

#### 2. Mock Server (Prototype)
<pre>
cd mockserver
npm install
npm run start
</pre>

#### 3. Monolithic Backend
<pre>
cd Backend
./mvnw spring-boot:run
</pre>

#### 4. Microservices Architecture
To run the full scalable system, start the services in this specific order:

1. **Service Discovery (Eureka):**
<pre>
cd MicroServices/Eureka
./mvnw spring-boot:run
</pre>

2. **API Gateway:**
<pre>
cd MicroServices/api-gateway
./mvnw spring-boot:run
</pre>

3. **Individual Services:**
<pre>
cd MicroServices/Services/&lt;service-name&gt;
./mvnw spring-boot:run
</pre>

---

## Tech Stack

| Component | Technologies Used |
| :--- | :--- |
| **Frontend** | React, Vite, CSS Modules, Axios, React Polling |
| **Mock Backend** | Node.js, Express, JSON Data |
| **Monolith** | Java, Spring Boot, Spring Security |
| **Microservices** | Spring Cloud, Eureka Server, API Gateway |
| **Database** | SQL (MySQL/PostgreSQL) |

---

## Configuration & Environment Setup

Before running the application, you must configure the database connections, ports, and security keys.

### 1. Backend Configuration (Spring Boot)
Update the `application.properties` file located in `src/main/resources` for the monolith or each microservice. You can customize the server port, database credentials, and JWT secrets here.

**Example `application.properties`:**

```properties
# Service Identification
spring.application.name=service-name

# Server Configuration (Change port as needed)
server.port=8080

# Service Discovery
eureka.client.serviceUrl.defaultZone=http://localhost:8760/eureka/
eureka.instance.hostname=localhost

# Database Configuration
spring.datasource.url=jdbc:mysql://localhost:3306/db_name
spring.datasource.driverClassName=com.mysql.cj.jdbc.Driver

# Set your actual database password here or use an environment variable
spring.datasource.username=root
spring.datasource.password=${DB_PASSWORD}

# JPA / Hibernate Settings
spring.jpa.database-platform=org.hibernate.dialect.MySQLDialect
spring.jpa.show-sql=true
spring.jpa.generate-ddl=true
spring.jpa.defer-datasource-initialization=true

# Security Configuration (JWT)
# IMPORTANT: Generate a secure key using: openssl rand -base64 32
spring.jwt.secret=${JWT_AUTH_KEY}
spring.jwt.expiration=86400000
```

---

## License

This project is licensed under the **MIT License**.

---

<p align="center"><em>Thank you for checking out OnePiece! Happy Bidding.</em></p>
