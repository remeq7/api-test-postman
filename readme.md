# 🧪 API Tests – Reqres (Postman + Newman)

This repository contains a Postman test collection for [reqres.in](https://reqres.in) – a fake REST API used for testing and prototyping.  
It includes sample requests, automated test scripts, and an HTML test report generated with Newman.

---

## 📁 Project Structure

```
api-test-postman/
├── collections/
│   └── api-tests-postman.postman_collection.json
├── environments/
│   └── reqres-env.postman_environment.json
├── newman-report/
│   └── report.html
├── README.md
```

---

## ✅ Covered Endpoints

- `GET /api/users`
- `GET /api/users/{id}`
- `POST /api/login`
- `POST /api/register`

Each request includes basic **Postman test assertions** (status codes, expected fields, etc).

---

## 🧪 How to Run Tests with Newman

### 1. Install Newman

> Make sure you have [Node.js](https://nodejs.org/) installed first

```bash
npm install -g newman
npm install -g newman-reporter-html
```

---

### 2. Run Collection & Generate Report

```bash
newman run collections/api-tests-postman.postman_collection.json   -e environments/reqres-env.postman_environment.json   -r html   --reporter-html-export newman-report/report.html
```

📝 This will run the full test suite and output an HTML report to `newman-report/`.

---

## 🔐 API Key Handling

This collection uses a free API key from reqres.in.  
To avoid hardcoding secrets, we use an environment variable:

```
x-api-key: {{api_key}}
```

Update the `api_key` variable in `environments/reqres-env.postman_environment.json`.

---

## 🧰 Tools Used

- Postman (Collection + Tests)
- Newman (CLI test runner)
- HTML Reporter (for clean reports)
