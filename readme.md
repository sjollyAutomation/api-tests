# 🧪 API Tests for Thinking Tester Contact List

This repository contains **Postman collections** and **environment configurations** for testing the public [Thinking Tester Contact List API](https://thinking-tester-contact-list.herokuapp.com/).

These tests validate key functionalities like:
- User registration and login
- Contact creation, retrieval, update, and deletion
- Authentication and data validation

---

## 🧰 Tools Used

| Tool | Purpose |
|------|----------|
| [Postman](https://www.postman.com/) | Create and manage API requests and tests |
| [Newman](https://github.com/postmanlabs/newman) | Run Postman collections via command line or CI/CD |
| [Newman Reporter HTMLExtra](https://github.com/DannyDainton/newman-reporter-htmlextra) | Generate detailed, visually rich test reports |

---

## 📁 Repository Structure

```text
api-tests/
├── README.md
└── postman/
    ├── collections/
    │   └── contact-list.postman_collection.json
    └── environments/
        └── contact-list.postman_environment.json
```

---

## ⚙️ Setup Instructions

### 1. Install Node.js
If you don’t have Node.js installed, download it from:
👉 [https://nodejs.org/](https://nodejs.org/)

### 2. Install Newman
```bash
npm install -g newman
```

### 3. Install Newman HTMLExtra Reporter
```bash
npm install -g newman-reporter-htmlextra
```

🚀 Running the Tests
Run the collection with the environment
```bash
newman run collections/<collection.json> -e environments/<environment.json>
```
Run with HTML Report
```bash
newman run collections/<collection.json> \
  -e environments/<environment.json> \
  -r htmlextra \
  --reporter-htmlextra-export ./reports/ContactListTestReport.html
```
Once the run completes, open the generated report file in your browser:

reports/ContactListTestReport.html
🔒 Notes on Environment Variables
Environment variables like contactListUrl, email, password, and token are stored in Requests.postman_environment.json.

Sensitive data (like tokens) are marked as sensitive in Postman and not visible in UI.

If you’re sharing the environment file publicly, ensure sensitive values are cleared before committing.

🧩 Example Variable Setup
Example environment variables for this API:

Variable	Example Value	Description
contactListUrl	https://thinking-tester-contact-list.herokuapp.com	Base API endpoint
email	your_email@example.com	User email for login/registration
password	your_password	User password
token	(set automatically after login)	JWT auth token used in subsequent requests

📊 Example Output
When using htmlextra, your test run report will look like this:

Summary of passed and failed requests

Detailed test assertions

Response time breakdowns

Request and response body previews

🧼 Maintenance Tips
Clean up .DS_Store and other local files using .gitignore

Keep environment values updated with valid credentials

Use Newman CLI for CI/CD integration (e.g., GitHub Actions, Jenkins)

🧠 About the API
The Thinking Tester Contact List API is a public RESTful service designed for learning and practicing API testing.
Documentation: https://thinking-tester-contact-list.herokuapp.com/

💬 Author
Jolly
🔗 GitHub: @sjollyAutomation

---