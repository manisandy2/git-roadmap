# Phase 01 – Git Fundamentals Practice

## Objective

Practice the basic Git workflow from creating a repository to viewing commit history.

---

# Exercise 1 – Initialize a Repository

### Step 1: Create a Project

```bash
mkdir git-practice
cd git-practice
```

### Step 2: Initialize Git

```bash
git init
```

### Verify

```bash
git status
```

**Expected Output**

```text
On branch main

No commits yet

nothing to commit
```

---

# Exercise 2 – Configure Git

Configure your identity.

```bash
git config user.name "Your Name"

git config user.email "your_email@example.com"
```

Verify:

```bash
git config user.name
git config user.email
```

---

# Exercise 3 – Create Your First File

Create a README file.

```bash
echo "# Git Practice" > README.md
```

Check status.

```bash
git status
```

**Expected Output**

```text
Untracked files:
    README.md
```

---

# Exercise 4 – Stage the File

```bash
git add README.md
```

Verify.

```bash
git status
```

**Expected Output**

```text
Changes to be committed:
    new file: README.md
```

---

# Exercise 5 – Commit the File

```bash
git commit -m "Initial commit"
```

Verify.

```bash
git status
```

**Expected Output**

```text
nothing to commit, working tree clean
```

---

# Exercise 6 – Create Another File

```bash
echo "print('Hello Git')" > app.py
```

Check status.

```bash
git status
```

---

# Exercise 7 – Stage All Files

```bash
git add .
```

Verify.

```bash
git status
```

---

# Exercise 8 – Second Commit

```bash
git commit -m "Add app.py"
```

---

# Exercise 9 – Modify a File

Append a line to the Python file.

```bash
echo "print('Git Fundamentals')" >> app.py
```

Check status.

```bash
git status
```

---

# Exercise 10 – Commit the Changes

```bash
git add app.py

git commit -m "Update app.py"
```

---

# Exercise 11 – View Commit History

Full history.

```bash
git log
```

Short history.

```bash
git log --oneline
```

Graph view.

```bash
git log --graph --oneline --decorate
```

---

# Exercise 12 – View Commit Summary

```bash
git shortlog

git shortlog -sn
```

---

# Mini Challenge

Complete the following tasks without looking at the notes:

* Create a new Git repository.
* Configure your username and email.
* Create a `README.md` file.
* Stage the file.
* Commit it.
* Create an `app.py` file.
* Commit it.
* Modify `app.py`.
* Commit the changes.
* Display the commit history.
* Display the commit graph.
* Display the shortlog.

---

# Expected Repository Structure

```text
git-practice/
│
├── .git/
├── README.md
└── app.py
```

---

# Final Result

After completing this practice, you should have:

* ✅ 1 Git repository
* ✅ 2 project files (`README.md` and `app.py`)
* ✅ 3 commits
* ✅ A clean working tree
* ✅ Experience using the core Git commands

---

# Self-Assessment Checklist

| Task                      | Status |
| ------------------------- | ------ |
| Installed Git             | ☐      |
| Configured username       | ☐      |
| Configured email          | ☐      |
| Initialized repository    | ☐      |
| Checked repository status | ☐      |
| Added files               | ☐      |
| Created commits           | ☐      |
| Viewed commit history     | ☐      |
| Viewed commit graph       | ☐      |
| Viewed shortlog           | ☐      |
