# 🍔 Foody API Test Automation

Automated RESTful API testing suite built for the **Foody** platform using **Postman**, **Newman**, and the **htmlextra reporter**.

---

## 🚀 Project Overview

This project validates the core functionalities of the Foody web application backend, ensuring reliable integration across user management, authentication, and food item lifecycle operations.

### ✨ Tested Endpoints:

1. **User Authentication:** POST `/api/User/Authentication` (Validates status codes, response structure, and dynamically stores `accessToken` as a Collection Variable).
2. **Food Management (CRUD):**
   - **Create:** POST `/api/Food/Create` (Uses a Pre-request script to generate dynamic test data).
   - **Search:** GET `/api/Food/Search` (Validates query parameters and response arrays).
   - **Edit:** PATCH `/api/Food/Edit/{foodId}` (Updates resource properties using JSON patch operations).
   - **Delete:** DELETE `/api/Food/Delete/{foodId}` (Ensures proper cleanup and status validation).

---

## 🛠️ Tech Stack & Tools

- **Postman:** API client used for designing test scripts and managing collection variables.
- **Newman:** Command-line companion for Postman, enabling continuous integration execution.
- **Newman HTML Extra Reporter:** Generates comprehensive, interactive execution dashboards.

---

## ⚙️ How to Run the Tests Locally

### Prerequisites

Make sure you have **Node.js** and **Newman** (with the htmlextra reporter) installed globally:

```bash
npm install -g newman
npm install -g newman-reporter-htmlextra
```

### Execution

Clone the repository and run the test collection via Newman with the following command:

```bash
newman run Foody.postman_collection -r htmlextra
```

---

## 📊 Test Report Preview

After execution, a detailed HTML report is automatically generated (saved in your repository as **`Foody-Report-Newman.html`**), displaying test pass rates, assertion details, and response metrics.
