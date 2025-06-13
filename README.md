# 💸 Smart Expense Tracker — IN PROGRESS 🚧

A cloud-ready, containerized expense tracker built with Java, Spring Boot, PostgreSQL, and Redis — designed for multi-user SaaS usage.

> 🧭 **Mission:** A secure, scalable backend for managing personal finances — helping users track expenses, set budgets, and stay financially informed.

---

### 🎯 Project Goal: Smart Expense Tracker

To build a **multi-user web application** where people can:

- ✅ Securely log in (using email/password or Google)
- 💸 Track their income and expenses
- 🎯 Set budgets for spending categories (like food, rent, etc.)
- 📈 See reports and graphs showing where their money goes
- 🔔 Get alerts if they overspend or for weekly summaries
- 🧠 Optionally, in the future, use smart suggestions (AI) to help them categorize and analyze spending

---

### 📌 Note  
_This is a **draft version** of the Smart Expense Tracker project. It outlines the intended architecture and features, but the implementation is still **in progress** and subject to change._

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
git clone https://github.com/shreya-sagar/smart-expense-tracker.git
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

- Architecture : [`docs/architecture.md`](docs/architecture.md)
- High-Level Design (HLD) : [`docs/HLD.md`](docs/HLD.md)
- Low-Level Design (LLD) : [`docs/LLD.md`](docs/LLD.md)
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

