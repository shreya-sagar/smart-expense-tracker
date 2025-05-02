# 💸 Smart Expense Tracker (Multi-User SaaS) - IN PROGRESS

A cloud-ready, containerized expense tracker built with Java, Spring Boot, PostgreSQL, and Redis. Designed to help users track incomes, expenses, budgets, and receive alerts with analytical reporting — all in a multi-user SaaS style.

---

## ✨ Features

- ✅ JWT & Google OAuth2 Authentication
- 💰 Income & Expense Tracking
- 📊 Budget Management
- 🔔 Alerts & Weekly Summary via Email
- ⚡ Redis Caching for Performance
- 🐳 Dockerized Deployment
- 📚 Swagger/OpenAPI Documentation
- 🧪 JUnit + Mockito Test Coverage

---

## 🧱 Tech Stack

| Layer         | Technology                         |
|---------------|-------------------------------------|
| Backend       | Spring Boot 3+, Spring Security     |
| Database      | PostgreSQL, JPA (Hibernate)         |
| Caching       | Redis                               |
| Scheduler     | Spring Scheduling                   |
| Email         | JavaMailSender / SendGrid           |
| Container     | Docker, Docker Compose              |
| API Docs      | SpringDoc (Swagger/OpenAPI)         |
| Testing       | JUnit5, Mockito                     |

---

## 🚀 Getting Started

### 🛠 Prerequisites
- Java 17+
- Docker & Docker Compose
- Maven

### 🔧 Setup Instructions

```bash
git clone https://github.com/your-username/smart-expense-tracker.git
cd smart-expense-tracker
./mvnw clean install
docker-compose up --build
```

### 📌 Services
- Backend: `http://localhost:8080`
- Swagger UI: `http://localhost:8080/swagger-ui.html`
- PostgreSQL: `localhost:5432`

---

## 📒 API Modules

### 🔐 Authentication
- JWT & OAuth2 Google Login
- Role-based access (`Admin`, `User`)

### 💸 Income & Expense
- CRUD operations on transactions
- Filter by category, date range

### 🎯 Budgets
- Set monthly category budgets
- Track against spending trends

### 📈 Reports
- Monthly summaries, category analytics
- Yearly trends

### ⏰ Alerts
- Email alerts on overspending
- Weekly summaries via scheduled jobs

---

## 🧪 Testing

- Unit Testing with JUnit5
- Mocking with Mockito
- Target Coverage: **80%+**

---

## 📘 Documentation

- Full documentation available at: [`docs/architecture.md`](docs/architecture.md)
- Swagger UI: `http://localhost:8080/swagger-ui.html`

---

## 📄 License

[MIT License](LICENSE)

---

## 🙌 Contributing

Feel free to raise issues or submit pull requests. Contributions and ideas are welcome!

---

## 🔮 Roadmap
- [ ] Multi-currency support
- [ ] AI-powered category suggestions
- [ ] Mobile app (React Native/Flutter)
- [ ] Subscription model for premium users

---

**Crafted with 💻 + ☕ by Shreya Sagar**

