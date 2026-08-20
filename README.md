<div align="center">

# 🏡 RealEstate

### Real Estate Management Backend API

*A layered Spring Boot REST API for property listings, CRM leads, viewings & more — powered by raw JDBC and Flyway.*

[![Java](https://img.shields.io/badge/Java-21-orange?style=for-the-badge&logo=openjdk&logoColor=white)](https://openjdk.org/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-4.1.0-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)](https://spring.io/projects/spring-boot)
[![MySQL](https://img.shields.io/badge/MySQL-8.0-4479A1?style=for-the-badge&logo=mysql&logoColor=white)](https://www.mysql.com/)
[![Maven](https://img.shields.io/badge/Maven-Build-C71A36?style=for-the-badge&logo=apachemaven&logoColor=white)](https://maven.apache.org/)

</div>

---

## 📖 About

**PrimeEstate** is a real estate management backend built to explore Spring Boot fundamentals *without* the JPA magic — every query is hand-written with `JdbcTemplate`, every schema change is version-controlled with Flyway, and the architecture stays strictly layered: **Controller → Service → Repository**.

It powers property listings, a mini-CRM for leads, viewing appointments, newsletter subscriptions, and even an AI chatbot for property inquiries.

---

## ✨ Features

| | Feature | Status |
|---|---|:---:|
| 🏠 | Property CRUD, search & pagination | ✅ |
| 👥 | Lead management (CRM-style) | 🔜 |
| 📊 | Lead pipeline stages (Kanban-style) | 🔜 |
| 📅 | Property viewing bookings | 🔜 |
| 📧 | Newsletter subscription + email | 🔜 |
| 🤖 | AI chatbot (GitHub AI Models) | 🔜 |

---

## 🧱 Tech Stack

<div align="center">

| Layer | Tech |
|---|---|
| **Language** | Java 21 |
| **Framework** | Spring Boot 4.1.0 |
| **Data Access** | Spring Data JDBC (`JdbcTemplate`) |
| **Database** | MySQL 8 |
| **Migrations** | Flyway |
| **Mapping** | Lombok · ModelMapper |
| **API Docs** | springdoc-openapi (Swagger UI) |
| **Email** | Spring Boot Starter Mail |
| **AI** | OpenAI Java SDK via GitHub AI Models |
| **Config** | `dotenv-java` |

</div>

---

## 📁 Project Structure

```
src/main/java/com/realestate/management/
├── 📂 config/          → ModelMapper bean, CORS setup
├── 📂 controller/       → REST endpoints
├── 📂 Dto/               → Request/response objects
├── 📂 entity/           → DB table models
├── 📂 enums/            → State, PropertyStatus
├── 📂 repository/
│   └── 📂 impl/         → JdbcTemplate queries
├── 📂 service/
│   └── 📂 impl/         → Business logic
└── 📂 util/              → ApiResponse, Page wrappers

src/main/resources/
├── ⚙️ application.yaml
└── 📂 db.migration/      → Flyway SQL scripts
```

---

## 🚀 Quick Start

### 1️⃣ Prerequisites

- ☕ JDK 21
- 🐬 MySQL Server 8.x
- 📦 Maven (or use the bundled `mvnw`)

### 2️⃣ Clone & enter the project

```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
```

### 3️⃣ Create the database

```sql
CREATE DATABASE realestate;
```

### 4️⃣ Configure your credentials

`src/main/resources/application.yaml`

```yaml
spring:
  datasource:
    url: jdbc:mysql://localhost:3306/realestate?useSSL=false&serverTimezone=UTC&allowPublicKeyRetrieval=true
    username: root
    password: your_mysql_password
```

### 5️⃣ Add environment variables

Create a `.env` in the project root:

```env
GITHUB_TOKEN=your_github_personal_access_token
```

> 🔑 Generate one at **GitHub → Settings → Developer Settings → Personal Access Tokens** with the `models: read` scope.

### 6️⃣ Run it

```bash
./mvnw spring-boot:run
```

🎉 Server's live at **`http://localhost:8080`** — Flyway migrates the schema automatically on boot.

### 7️⃣ Explore the API

```
http://localhost:8080/swagger-ui/index.html
```

---

## 📡 API Reference

<details>
<summary><b>🏠 Property Endpoints</b></summary>

| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/api/property/add` | Create a new listing |
| `GET` | `/api/property/get-all` | Fetch all properties |
| `GET` | `/api/property/get-by-id/{id}` | Fetch a single property |
| `GET` | `/api/property/get-count` | Total property count |

</details>

---

<div align="center">

Built with ☕ and a lot of `JdbcTemplate` queries.

</div>
