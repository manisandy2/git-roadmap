# Phase 03 – Branching Practice

## Objective

Learn how to create, switch, merge, and delete branches, and resolve merge conflicts using Git.

---

# Learning Outcomes

After completing this practice, you will be able to:

* Create new branches
* List all branches
* Switch between branches
* Create and switch to a branch in one command
* Merge branches
* Delete merged branches
* Resolve merge conflicts

---

# Prerequisites

Create a practice repository.

```bash
mkdir git-phase3-practice

cd git-phase3-practice

git init
```

Create a file.

```bash
echo "# Git Branching Practice" > README.md
```

Stage and commit.

```bash
git add .

git commit -m "Initial commit"
```

---

# Exercise 1 – View Current Branch

Display the current branch.

```bash
git branch
```

Expected Output

```text
* main
```

---

# Exercise 2 – Create a Branch

Create a feature branch.

```bash
git branch feature-login
```

Verify.

```bash
git branch
```

Expected Output

```text
* main
  feature-login
```

---

# Exercise 3 – Switch to the Branch

```bash
git switch feature-login
```

Verify.

```bash
git branch
```

Expected Output

```text
* feature-login
  main
```

---

# Exercise 4 – Create and Switch in One Command

```bash
git switch -c feature-dashboard
```

Verify.

```bash
git branch
```

---

# Exercise 5 – Add a Feature

Create a new file.

```bash
echo "Login Feature" > login.py
```

Stage and commit.

```bash
git add .

git commit -m "Add login feature"
```

View history.

```bash
git log --oneline --graph
```

---

# Exercise 6 – Merge a Branch

Switch back to the main branch.

```bash
git switch main
```

Merge the feature branch.

```bash
git merge feature-login
```

Verify.

```bash
git log --graph --oneline --decorate
```

---

# Exercise 7 – Delete a Branch

Delete the merged branch.

```bash
git branch -d feature-login
```

List branches.

```bash
git branch
```

---

# Exercise 8 – Force Delete a Branch

Create a new branch.

```bash
git switch -c feature-payment
```

Create a file.

```bash
echo "Payment Feature" > payment.py
```

Return to the main branch.

```bash
git switch main
```

Force delete the branch.

```bash
git branch -D feature-payment
```

---

# Exercise 9 – List Branches

Show local branches.

```bash
git branch
```

Show latest commit.

```bash
git branch -v
```

Merged branches.

```bash
git branch --merged
```

Unmerged branches.

```bash
git branch --no-merged
```

---

# Exercise 10 – Merge Conflict

Create a new branch.

```bash
git switch -c feature-profile
```

Create a file.

```bash
echo "Profile Page" > app.py
```

Commit.

```bash
git add .

git commit -m "Profile feature"
```

Switch back.

```bash
git switch main
```

Modify the same file.

```bash
echo "Main Branch Version" > app.py
```

Commit.

```bash
git add .

git commit -m "Main update"
```

Merge.

```bash
git merge feature-profile
```

Git reports a conflict.

Example:

```text
<<<<<<< HEAD
Main Branch Version
=======
Profile Page
>>>>>>> feature-profile
```

Resolve the conflict.

Example:

```text
Main Branch Version
Profile Page
```

Stage the resolved file.

```bash
git add app.py
```

Complete the merge.

```bash
git commit
```

---

# Exercise 11 – Merge Using a Merge Commit

Create another feature branch.

```bash
git switch -c feature-search
```

Commit some work.

```bash
echo "Search Feature" > search.py

git add .

git commit -m "Add search feature"
```

Merge using a merge commit.

```bash
git switch main

git merge --no-ff feature-search
```

View history.

```bash
git log --graph --oneline --decorate
```

---

# Exercise 12 – Complete Branch Workflow

```bash
git switch main

git pull

git switch -c feature-notification

echo "Notification Feature" > notification.py

git add .

git commit -m "Add notification feature"

git switch main

git merge feature-notification

git branch -d feature-notification
```

---

# Mini Challenge

Without referring to the notes, complete the following:

* Create a branch.
* Switch to it.
* Create a file.
* Commit the file.
* Switch back to the main branch.
* Merge the feature branch.
* Delete the merged branch.
* Create another branch.
* Cause a merge conflict.
* Resolve the conflict successfully.

---

# Expected Repository Structure

```text
git-phase3-practice/
│
├── .git/
├── README.md
├── app.py
├── login.py
├── search.py
└── notification.py
```

---

# Common Commands

| Command                      | Description                   |
| ---------------------------- | ----------------------------- |
| `git branch`                 | List local branches           |
| `git branch <name>`          | Create a branch               |
| `git branch -v`              | Show branch details           |
| `git branch --merged`        | List merged branches          |
| `git branch --no-merged`     | List unmerged branches        |
| `git switch <branch>`        | Switch branches               |
| `git switch -c <branch>`     | Create and switch to a branch |
| `git merge <branch>`         | Merge a branch                |
| `git merge --no-ff <branch>` | Merge with a merge commit     |
| `git branch -d <branch>`     | Delete a merged branch        |
| `git branch -D <branch>`     | Force delete a branch         |

---

# Self-Assessment Checklist

| Task                                | Status |
| ----------------------------------- | ------ |
| Created a branch                    | ☐      |
| Switched branches                   | ☐      |
| Created and switched in one command | ☐      |
| Merged a branch                     | ☐      |
| Deleted a merged branch             | ☐      |
| Force deleted a branch              | ☐      |
| Listed merged branches              | ☐      |
| Listed unmerged branches            | ☐      |
| Resolved a merge conflict           | ☐      |

---

# Outcome

After completing **Phase 03 – Branching**, you will be able to:

* Create and manage feature branches.
* Switch between branches safely.
* Merge branches into `main`.
* Delete branches after merging.
* Understand fast-forward and merge commits.
* Resolve merge conflicts confidently.
* Follow a real-world feature branch workflow.
