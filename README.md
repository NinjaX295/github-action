# 🚀 GitHub Actions CI Setup Guide

> A simple guide to help you set up a **GitHub Action** for Continuous Integration (CI) in your project.

---

## ✨ What is GitHub Actions?

**GitHub Actions** lets you automate, customize, and execute your software development workflows right in your GitHub repository. It's commonly used for CI/CD pipelines.

---

## 📁 Project Structure (Sample)
``` bash
your-repo/
│
├── .github/
│ └── workflows/
│ └── ci.yml <-- Your GitHub Actions workflow file
│
├── src/
│ └── your-code.js
├── tests/
│ └── your-tests.test.js
├── package.json
└── README.md
```

1. In your project root, create folders:
   ```bash
   mkdir -p .github/workflows
2. touch .github/workflows/ci.yml
 add the following inside your ci.yml file
 ```bash
 name: 🚨 Run Tests

on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

jobs:
  test:
    runs-on: ubuntu-latest

    steps:
    - name: 📥 Checkout code
      uses: actions/checkout@v4

    - name: 🟢 Setup Node.js
      uses: actions/setup-node@v4
      with:
        node-version: '18'

    - name: 📦 Install dependencies
      run: npm ci

    - name: ✅ Run tests
      run: npm test
```

 
