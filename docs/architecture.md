# 📐 Smart Expense Tracker — Architecture Documentation

## 🧩 Overview
A multi-user SaaS backend system that enables users to manage personal finances: log transactions, set budgets, receive alerts, generate reports, and analyze trends. Built using Java Spring Boot with PostgreSQL and Redis, secured via JWT and Google OAuth2, and cloud-deployable using Docker.

---

## 🔧 Backend Modules

### 1. **Authentication Module**
- Login/Signup using JWT
- OAuth2 Google Login Integration
- User roles: `ROLE_USER`, `ROLE_ADMIN`

### 2. **User Module**
- Register user
- Update profile
- Fetch user details

### 3. **Transaction Module**
- Add/Edit/Delete incomes and expenses
- Filter by category, date, type
- Calculate totals

### 4. **Budget Module**
- Set monthly budgets per category
- Track spending against budget
- Get over-budget alerts

### 5. **Report Module**
- Generate monthly, quarterly, yearly summaries
- Expense distribution charts (Pie/Bar)

### 6. **Alert Scheduler Module**
- Email alerts for overspending
- Weekly summary emails

### 7. **Caching Layer (Redis)**
- Cache reports and frequent queries

### 8. **Admin Module (Optional)**
- View users
- Delete accounts
- Usage analytics

---

## 🔐 Security
- **Spring Security**: Secures all endpoints
- **JWT**: Token-based access for frontend
- **Google OAuth2**: Alternate login via Google
- **Role-based Authorization**: Admin/User access control

---

## 🗃 Database Design

### PostgreSQL Tables

#### `users`
| Column        | Type      | Description            |
|---------------|-----------|------------------------|
| id            | UUID      | Primary Key            |
| name          | String    | Full name              |
| email         | String    | Unique email           |
| password      | String    | Encrypted password     |
| provider      | String    | `LOCAL` or `GOOGLE`    |
| role          | Enum      | `ROLE_USER` or `ADMIN` |
| created_at    | Timestamp |                        |

#### `transactions`
| Column        | Type      | Description            |
|---------------|-----------|------------------------|
| id            | UUID      | Primary Key            |
| user_id       | UUID      | FK to users            |
| type          | Enum      | `INCOME` or `EXPENSE`  |
| category      | String    | e.g. Food, Salary      |
| amount        | Decimal   |                        |
| description   | String    | Optional note          |
| date          | Date      |                        |

#### `budgets`
| Column        | Type      | Description            |
|---------------|-----------|------------------------|
| id            | UUID      | Primary Key            |
| user_id       | UUID      | FK to users            |
| category      | String    | Budget category        |
| amount        | Decimal   | Monthly budget         |
| month         | String    | e.g. 2025-05           |

---

## 🧠 Caching Strategy (Redis)
- Cache user reports for 1–3 hours
- Use Redis keys like `report:{userId}:{month}`

---

## ⏰ Scheduler
- Weekly summary emails: Sunday at 8AM
- Overspending alerts: Triggered post transaction insert

---

## 📤 Email Service
- Uses Spring’s `JavaMailSender`
- Templated emails using Thymeleaf or plain HTML

---

## 🧪 Testing
- JUnit + Mockito for all services
- Integration Tests using `@SpringBootTest`
- Target: 80%+ code coverage

---

## 🐳 Docker Setup
- Spring Boot app image
- PostgreSQL container
- Redis container
- `docker-compose.yml` to orchestrate

---

## 🔍 Swagger/OpenAPI
- Accessible at `/swagger-ui.html`
- Auto-generated using SpringDoc

---

## 📈 Metrics (Optional Extension)
- Add Spring Boot Actuator
- Expose `/actuator/metrics`

---

## 🔮 Future Enhancements
- Multi-currency support
- Notification system using WebSocket
- Subscription/paywall integration
- Export reports to PDF/Excel

---

**Maintained by: Shreya Sagar — Java & Spring Backend Developer**

