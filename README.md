# 🍔 Foody API Test Automation

This repository contains a Postman collection and Newman-based test suite for validating the Foody backend API. The collection exercises the main authentication and food-management flows and verifies expected response codes and payloads.

---

## 🚀 Project Overview

The project checks whether the Foody API behaves correctly across the most important user and food workflows, including:

- user creation
- user authentication
- food creation
- food search
- food update
- food deletion

The tests are designed to validate status codes, response structure, and important dynamic values such as authentication tokens and created food IDs.

### ✨ Tested Endpoints

1. **Create User** — `POST /api/User/Create`
2. **User Authentication** — `POST /api/User/Authentication`
3. **Create Food** — `POST /api/Food/Create`
4. **Search Food** — `GET /api/Food/Search?keyword={{randomFood}}`
5. **Edit Food** — `PATCH /api/Food/Edit/{{foodId}}`
6. **Delete Food** — `DELETE /api/Food/Delete/{{foodId}}`

---

## 🛠️ Tech Stack & Tools

- **Postman** — used to design and manage the API test collection
- **Newman** — runs the Postman collection from the command line
- **newman-reporter-htmlextra** — generates an HTML test report

---

## ⚙️ How to Run the Tests Locally

### Prerequisites

Make sure you have Node.js and npm installed, then install the required Newman packages globally:

```bash
npm install -g newman
npm install -g newman-reporter-htmlextra
```

### Run the Collection

From the repository root, execute:

```bash
newman run Foody.postman_collection.json -r cli,htmlextra --reporter-htmlextra-export "Foody-Report-Newman.html"
```

This will run the collection and generate an HTML report named `Foody-Report-Newman.html` in the current directory.

### Notes

- The collection includes variables such as `baseURL`, `token`, `randomFood`, and `foodId`.
- If you are pointing the tests at a different environment, update the relevant collection variables before running the suite.
- The current collection file already contains a default API base URL and token value, so it can be run as-is for the configured environment.

---

## 📊 Test Report Preview

A sample HTML report is already included in the repository as `Foody-Report-Newman.html`. It contains execution summaries, test pass/fail information, and response details for the test run.

---

## Repository Files

- `Foody.postman_collection.json` — Postman collection with requests and tests
- `Foody-Report-Newman.html` — generated HTML execution report
- `README.md` — project documentation
