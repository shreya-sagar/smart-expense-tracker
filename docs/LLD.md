# 🧰 Low-Level Design (LLD) — Smart Expense Tracker

## 📦 Project Structure (Maven-style)

```
com.
.expensetracker
├── config
│   └── SecurityConfig.java
├── controller
│   ├── AuthController.java
│   ├── TransactionController.java
│   └── BudgetController.java
├── dto
│   ├── AuthRequest.java
│   ├── TransactionDto.java
│   └── BudgetDto.java
├── entity
│   ├── User.java
│   ├── Transaction.java
│   └── Budget.java
├── exception
│   ├── GlobalExceptionHandler.java
│   └── CustomExceptions.java
├── repository
│   ├── UserRepository.java
│   ├── TransactionRepository.java
│   └── BudgetRepository.java
├── service
│   ├── AuthService.java
│   ├── TransactionService.java
│   └── BudgetService.java
└── scheduler
    └── AlertScheduler.java
```

---

## 📑 Entity Design

### `User`

```java
class User {
    UUID id;
    String name;
    String email;
    String password;
    AuthProvider provider; // LOCAL, GOOGLE
    Role role;             // ROLE_USER, ROLE_ADMIN
    Timestamp createdAt;
}
```

### `Transaction`

```java
class Transaction {
    UUID id;
    UUID userId;
    TransactionType type; // INCOME, EXPENSE
    String category;
    BigDecimal amount;
    String description;
    LocalDate date;
}
```

### `Budget`

```java
class Budget {
    UUID id;
    UUID userId;
    String category;
    BigDecimal amount;
    String month; // e.g. "2025-05"
}
```

---

## 🔐 Authentication Flow

1. User logs in via Google or Email/Password
2. JWT is generated and returned
3. Token is stored in frontend, sent on each API call

---

## 🔁 Service Layer Example (TransactionService)

```java
public List<TransactionDto> getTransactionsForUser(UUID userId, LocalDate start, LocalDate end) {
    List<Transaction> txs = txRepo.findByUserIdAndDateBetween(userId, start, end);
    return txs.stream().map(mapper::toDto).collect(Collectors.toList());
}
```

---

## ⏰ Scheduler (AlertScheduler)

```java
@Scheduled(cron = "0 0 8 * * SUN")
public void sendWeeklySummaryEmails() {
    // Fetch users, generate summary, send mail
}
```

---

## ✉️ Email Templates

* `/resources/templates/weekly-summary.html`
* `/resources/templates/over-budget-alert.html`

---

## 🧪 Unit Test Example

```java
@Test
void testGetTransactions() {
    when(txRepo.findByUserIdAndDateBetween(...)).thenReturn(...);
    // Assertions
}
```

---

## 🧾 API Endpoint Sample

### POST `/api/transactions`

```json
{
  "type": "EXPENSE",
  "category": "Groceries",
  "amount": 125.50,
  "date": "2025-05-03",
  "description": "Weekly grocery run"
}
```

---
