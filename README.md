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

## ⭐ Bonus Task: Self-Hosted Runner

### What is a Self-Hosted Runner?
A self-hosted runner is a machine (e.g., your local server or VM) that runs GitHub Actions jobs instead of GitHub's cloud infrastructure.

### 🔧 How to Set One Up

1. **Go to your repo on GitHub → Settings → Actions → Runners → Add Runner**

2. **Choose OS** (Linux/Windows/macOS) and architecture

3. **Follow GitHub’s instructions**, e.g. for Linux:
```bash
mkdir actions-runner && cd actions-runner
curl -o actions-runner-linux-x64-2.315.0.tar.gz -L https://github.com/actions/runner/releases/download/v2.315.0/actions-runner-linux-x64-2.315.0.tar.gz
tar xzf ./actions-runner-linux-x64-2.315.0.tar.gz
./config.sh --url https://github.com/your-username/your-repo --token YOUR_TOKEN_HERE
./run.sh
```


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

