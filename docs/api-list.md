# 📡 API Endpoints List — Smart Expense Tracker (Tentative)

## 🛡 AuthController

* `POST /api/auth/register` → Register new user
* `POST /api/auth/login` → Login with credentials
* `GET /api/auth/google` → OAuth2 login redirect

## 💰 TransactionController

* `GET /api/transactions` → Fetch user’s transactions
* `POST /api/transactions` → Add income/expense
* `DELETE /api/transactions/{id}` → Delete by ID

## 🎯 BudgetController

* `GET /api/budgets` → Get budget list
* `POST /api/budgets` → Set or update budget
* `DELETE /api/budgets/{id}` → Remove budget

## 📊 ReportController

* `GET /api/reports/summary` → Summary by time range
* `GET /api/reports/trends` → Trend analysis

## 🚨 NotificationController

* `GET /api/alerts` → Fetch alerts
* `POST /api/alerts/test` → Trigger test alert

---

**All endpoints are protected by JWT auth headers.**

* Use: `Authorization: Bearer <token>`
* Swagger docs available at: `/swagger-ui.html`
