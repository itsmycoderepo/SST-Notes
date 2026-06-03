# 🐍 Python for DevOps/SRE - Day 1

---

# 🎯 Learning Objectives

By the end of this session, you will understand:

* What Python is
* Why Python is important for DevOps/SRE
* Python Syntax and Semantics
* Python Interpreter vs Compiler
* Comments
* Variables
* Variable Naming Rules
* Naming Conventions
* Your First Python Program

---

# What is Python?

Python is a **High-Level Programming Language**.

✅ Easy to Learn

✅ Easy to Read

✅ Easy to Write

✅ Widely Used in DevOps, Cloud, Automation, AI, and Data Science

---

## Why is Python Popular?

Imagine you want to:

* Create AWS EC2 Instances
* Create Users Automatically
* Monitor Servers
* Send Alerts
* Analyze Logs

Python can do all of these with very little code.

---

# Syntax vs Semantics

## Syntax

Syntax refers to the **rules of writing code**.

Think of Syntax as grammar in English.

### Correct Syntax

```python
print("Hello World")
```

### Incorrect Syntax

```python
print("Hello World"
```

Python will throw an error because the syntax is incorrect.

---

## Semantics

Semantics refers to the **meaning of the code**.

Example:

```python
age = 25
```

Python understands that a variable called `age` is storing the value `25`.

---

# Python File Extension

Python files are saved with:

```text
.py
```

Examples:

```text
app.py
main.py
script.py
health_check.py
```

---

# Python Interpreter

Python is an **Interpreted Language**.

The interpreter reads and executes code.

## How Python Works

```text
Python Code
      │
      ▼
 Python Interpreter
      │
      ▼
 Machine Instructions
      │
      ▼
     Output
```

Example:

```python
print("Hello")
print("Welcome")
print("Python")
```

The interpreter executes these statements one by one.

---

# Compiler vs Interpreter

| Interpreter                | Compiler                        |
| -------------------------- | ------------------------------- |
| Executes code line by line | Converts entire program at once |
| Easier for debugging       | Faster execution                |
| Python                     | C                               |
| Shell Script               | C++                             |
| JavaScript                 | Go                              |

---

# Why Python for DevOps/SRE?

Python helps automate repetitive tasks.

Instead of doing a task manually 100 times, write a script once and run it whenever needed.

---

# Use Cases of Python in DevOps/SRE

## 1️⃣ Automation

Automate repetitive tasks such as:

* Creating users
* Password resets
* Backup management
* Log cleanup
* Report generation

### Example

Delete logs older than 30 days automatically.

---

## 2️⃣ Infrastructure Management

Manage cloud resources using code.

Examples:

* AWS EC2
* AWS S3
* Security Groups
* Load Balancers
* Virtual Machines

### Example

Create 10 EC2 servers automatically.

---

## 3️⃣ Monitoring & Alerting

Monitor systems and notify teams.

Examples:

* CPU Usage
* Memory Usage
* Disk Space
* Service Health

### Example

Send an alert when disk usage exceeds 90%.

---

## 4️⃣ CI/CD Pipelines

Python can help automate:

* Build validation
* Testing
* Release Notes
* Deployments

### Example

Trigger deployment after successful tests.

---

## 5️⃣ Kubernetes Automation

Manage Kubernetes resources.

Examples:

* Create Pods
* Scale Deployments
* Monitor Clusters
* Manage Containers

### Example

Scale application from 3 Pods to 10 Pods automatically.

---

## 6️⃣ Log Analysis

Analyze large log files.

Examples:

* Find Errors
* Find Warnings
* Generate Reports
* Detect Failures

---

# Shell Scripting vs Python

| Shell Scripting             | Python                               |
| --------------------------- | ------------------------------------ |
| Linux/Unix focused          | Cross-platform                       |
| Good for command automation | Good for automation and applications |
| Limited error handling      | Powerful error handling              |
| Less reusable               | Highly reusable                      |
| Basic JSON support          | Excellent JSON support               |
| Small scripts               | Small and large projects             |
| Limited libraries           | Huge ecosystem                       |

---

## When Should You Use Shell Script?

Use Shell Script when:

* Running Linux commands
* Creating cron jobs
* File operations
* Simple automation

---

## When Should You Use Python?

Use Python when:

* Working with AWS
* Working with Azure
* Calling APIs
* Infrastructure Automation
* Monitoring Systems
* Kubernetes Automation

---

# Python Syntax Rules

## Indentation

Python uses indentation to define blocks of code.

⚠️ Indentation is mandatory.

### Correct Example

```python
if True:
    print("Hello")
```

### Wrong Example

```python
if True:
print("Hello")
```

This will produce an error.

---

# Comments

Comments help explain code.

Python ignores comments during execution.

---

## Single Line Comment

```python
# This is a comment
```

Example:

```python
# Display welcome message
print("Welcome")
```

---

## Multi-Line Comment

```python
"""
This is a
multi-line comment
"""
```

Example:

```python
"""
This script checks
server health
"""
```

---

# Variables

A variable is used to store data.

Think of a variable as a container.

```text
Variable
   │
   ▼
 Stores Data
```

Example:

```python
name = "John"
age = 25
salary = 50000
```

---

# Rules for Naming Variables

## ✅ Allowed

* Start with a letter
* Start with underscore (_)
* Use numbers after the first character
* Use underscores

Examples:

```python
name
employee_id
emp1
_myvariable
```

---

## ❌ Not Allowed

Cannot start with a number.

```python
1name
```

Cannot contain special characters.

```python
employee-id
employee@id
```

Cannot use reserved keywords.

```python
class
if
for
while
```

---

# Variables are Case Sensitive

Python treats these as different variables:

```python
name = "John"

Name = "Mike"

NAME = "David"
```

All three are different.

---

# Naming Conventions

Good naming makes code easier to understand.

---

## Camel Case

First word starts with lowercase.

Remaining words start with uppercase.

Example:

```python
myEmployeeId
studentName
```

---

## Pascal Case

Every word starts with uppercase.

Example:

```python
MyEmployeeId
StudentName
```

---

## Snake Case ⭐ Recommended

All words are lowercase and separated using `_`.

Example:

```python
my_employee_id
student_name
server_health_report
```

Python's official style guide (PEP-8) recommends **Snake Case**.

---

# Python Keywords

Keywords are reserved words.

They cannot be used as variable names.

Examples:

```python
if
else
for
while
class
def
return
import
```

---

# First Python Program

```python
print("Hello World")
```

Output:

```text
Hello World
```

---

# Quick Recap

✅ Python is a High-Level Language

✅ Python is Interpreted

✅ Python files use `.py`

✅ Indentation is Mandatory

✅ Comments improve readability

✅ Variables store data

✅ Variable names follow rules

✅ Snake Case is Recommended

✅ Python is heavily used in DevOps and SRE

---

# Real-World DevOps Example

Suppose you have 500 Linux servers.

Without Python:

❌ Login to each server manually

❌ Check disk usage manually

❌ Send reports manually

With Python:

✅ Check all 500 servers automatically

✅ Generate reports automatically

✅ Send alerts automatically

This is why Python is one of the most important skills for a DevOps Engineer.

---
* Boolean
* Type Checking
* Type Conversion

Happy Learning! 🚀
