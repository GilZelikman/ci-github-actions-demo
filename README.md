# GitHub Actions CI Example

This repository demonstrates a basic Continuous Integration (CI) setup using **GitHub Actions** for a Python project. It includes two tasks:

---

## ✅ Task 1: Basic CI Workflow

* Triggered on every push to the `main` branch.
* Checks out the repository code using `actions/checkout@v3`.
* Prints a greeting message:

---

## ✅ Task 2: Running Tests

* Includes a simple Python function in `main.py` and corresponding unit tests in `test_main.py`.
* The GitHub Actions workflow:
* Sets up Python 3.9 using `actions/setup-python@v4`.
* Installs dependencies if a `requirements.txt` file exists.
* Runs the unit tests using Python’s built-in `unittest` framework.

---

## 🛠 GitHub Actions Workflow

The main workflow file is located at:


It performs the following steps:

1. **Check out the code**
2. **Print a CI greeting**
3. **Set up Python 3.9**
4. **Install dependencies (optional)**
5. **Run all unit tests**

---

## 📁 Project Structure

```
├── .github/
│ └── workflows/
│ └── ci.yml
├── main.py
├── test_main.py
├── requirements.txt (optional)
└── README.md

```
---

## 💡 Run Tests Locally

To run the tests manually on your machine:

```
python -m unittest discover
This will discover and run all tests in files named test*.py.

✅ Expected Output in CI
markdown

Hello, CI with GitHub Actions!
..
----------------------------------------------------------------------
Ran 2 tests in 0.000s

OK
📦 Requirements
Python 3.9+


📘 License
This project is licensed under the MIT License.
