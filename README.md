# GitHub Actions CI Example

This repository demonstrates a basic Continuous Integration (CI) setup using **GitHub Actions** for a Python project. It includes multiple automated workflows covering CI, testing, scheduling, and matrix builds.

---

## ✅ Task 1: Basic CI Workflow

- Triggered on every push to the `main` branch.
- Checks out the repository code using `actions/checkout@v3`.
- Prints a greeting message:  
  `Hello, CI with GitHub Actions!`

---

## ✅ Task 2: Running Tests

- Includes a simple Python function in `main.py` and corresponding unit tests in `test_main.py`.
- The GitHub Actions workflow:
  - Sets up Python using matrix versions: **3.7, 3.8, 3.9, 3.10**
  - Installs dependencies (if `requirements.txt` exists).
  - Runs the unit tests using Python’s built-in `unittest` framework.

---

## ✅ Task 3: Cron Scheduling

- A separate GitHub Actions workflow runs **daily at midnight UTC**.
- It performs:
  - Code checkout
  - Prints the message:  
    `Scheduled build completed successfully!`

---

## ✅ Task 4: Matrix Builds

- Enhances Task 2 by running tests across **multiple Python versions**.
- Uses GitHub Actions matrix strategy to test with Python:  
  `3.7`, `3.8`, `3.9`, and `3.10`.

---

## 🛠 GitHub Actions Workflow


Main Workflow : 
CI Workflow with Matrix Builds (ci.yml)
Runs on push to `main`.
It performs the following steps:

1. **Check out the code**
2. **Print a CI greeting**
3. **Set up Python 3.7,3.8,3.9,3.10**
4. **Install dependencies (optional)**
5. **Run all unit tests**

Second Workflow : 
Daily Scheduled Workflow (scheduled.yml)
It performs the following steps:
1. **Runs on 00:00 UTC Daily (Cron Scheduled)**
2. **Check out the code**
3. **Print build message**

---

## 📁 Project Structure

```
├── .github/
│ └── workflows/
│ └── ci.yml
│ └── scheduled.yml
├── main.py
├── test_main.py
├── requirements.txt (optional)
└── README.md

```
---

