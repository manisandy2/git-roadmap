# Phase 05 – Undo Operations Practice

## Objective

Learn how to safely undo changes in Git using `git commit --amend`, `git revert`, `git reset`, and `git reflog`.

---

# Learning Outcomes

After completing this practice, you will be able to:

* Amend the last commit
* Revert a commit safely
* Reset commits using soft, mixed, and hard modes
* Understand how reset affects the working directory and staging area
* Recover lost commits using `git reflog`

---

# Prerequisites

Create a practice repository.

```bash
mkdir git-phase5-practice

cd git-phase5-practice

git init
```

Create a file.

```bash
echo "Version 1" > app.py
```

Commit it.

```bash
git add .

git commit -m "Initial commit"
```

---

# Exercise 1 – Create Multiple Commits

Append new content.

```bash
echo "Version 2" >> app.py

git add .

git commit -m "Second commit"
```

Again.

```bash
echo "Version 3" >> app.py

git add .

git commit -m "Third commit"
```

Verify.

```bash
git log --oneline
```

Expected Output

```text
a1b2c3 Third commit
d4e5f6 Second commit
g7h8i9 Initial commit
```

---

# Exercise 2 – Amend the Last Commit Message

Rename the last commit.

```bash
git commit --amend -m "Updated third commit"
```

Verify.

```bash
git log --oneline
```

Notice that the latest commit hash has changed.

---

# Exercise 3 – Amend by Adding a Forgotten File

Create a README.

```bash
echo "# Git Undo Practice" > README.md
```

Stage it.

```bash
git add README.md
```

Add it to the previous commit.

```bash
git commit --amend --no-edit
```

Verify.

```bash
git log --stat
```

---

# Exercise 4 – Revert the Last Commit

Undo the last commit safely.

```bash
git revert HEAD
```

View history.

```bash
git log --oneline
```

Notice that Git creates a new commit instead of deleting history.

---

# Exercise 5 – Soft Reset

Create another commit.

```bash
echo "Version 4" >> app.py

git add .

git commit -m "Fourth commit"
```

Reset softly.

```bash
git reset --soft HEAD~1
```

Verify.

```bash
git status
```

Expected Output

```text
Changes to be committed
```

The changes remain staged.

---

# Exercise 6 – Mixed Reset

Reset again.

```bash
git reset --mixed HEAD
```

or

```bash
git reset HEAD
```

Verify.

```bash
git status
```

Expected Output

```text
Changes not staged for commit
```

The files remain, but they are unstaged.

---

# Exercise 7 – Hard Reset

Create another commit.

```bash
git add .

git commit -m "Temporary commit"
```

Reset hard.

```bash
git reset --hard HEAD~1
```

Verify.

```bash
git log --oneline
```

The last commit is removed.

---

# Exercise 8 – Reset to a Specific Commit

View commit hashes.

```bash
git log --oneline
```

Reset.

```bash
git reset --hard <commit_hash>
```

Example.

```bash
git reset --hard a1b2c3
```

---

# Exercise 9 – Recover Using Reflog

View the reflog.

```bash
git reflog
```

Example.

```text
abc111 HEAD@{0}: reset: moving to HEAD~1

def222 HEAD@{1}: commit: Temporary commit
```

Recover.

```bash
git reset --hard def222
```

Verify.

```bash
git log --oneline
```

The deleted commit has returned.

---

# Exercise 10 – Compare Reset Modes

Create another commit.

```bash
echo "Version 5" >> app.py

git add .

git commit -m "Version 5"
```

Practice each reset.

Soft

```bash
git reset --soft HEAD~1
```

Mixed

```bash
git reset --mixed HEAD
```

Hard

```bash
git reset --hard HEAD
```

Observe the difference after each command using:

```bash
git status
```

---

# Exercise 11 – Undo Workflow

Complete the following workflow.

```bash
echo "Testing Undo" >> app.py

git add .

git commit -m "Testing"

git commit --amend -m "Updated Testing"

git revert HEAD

git reset --soft HEAD~1

git reset --mixed HEAD

git reflog
```

---

# Exercise 12 – Recovery Challenge

Delete the latest commit.

```bash
git reset --hard HEAD~1
```

Recover it using only:

```bash
git reflog
```

Restore it.

```bash
git reset --hard <hash>
```

---

# Mini Challenge

Complete the following without looking at the notes:

* Create three commits.
* Amend the latest commit.
* Add a forgotten file using amend.
* Revert the latest commit.
* Practice `reset --soft`.
* Practice `reset --mixed`.
* Practice `reset --hard`.
* Recover the deleted commit using `git reflog`.

---

# Expected Repository Structure

```text
git-phase5-practice/
│
├── .git/
├── README.md
└── app.py
```

---

# Common Commands

| Command                        | Description                                       |
| ------------------------------ | ------------------------------------------------- |
| `git commit --amend`           | Edit the latest commit                            |
| `git commit --amend --no-edit` | Add staged changes to the last commit             |
| `git revert HEAD`              | Create a new commit that undoes the latest commit |
| `git revert <commit>`          | Revert a specific commit                          |
| `git reset --soft HEAD~1`      | Remove the latest commit and keep changes staged  |
| `git reset --mixed HEAD~1`     | Remove the latest commit and unstage changes      |
| `git reset --hard HEAD~1`      | Remove the latest commit and discard changes      |
| `git reset --hard <hash>`      | Reset to a specific commit                        |
| `git reflog`                   | Show HEAD history                                 |
| `git log --oneline`            | View commit history                               |

---

# Self-Assessment Checklist

| Task                                           | Status |
| ---------------------------------------------- | ------ |
| Amended a commit                               | ☐      |
| Added forgotten files using amend              | ☐      |
| Reverted a commit                              | ☐      |
| Practiced soft reset                           | ☐      |
| Practiced mixed reset                          | ☐      |
| Practiced hard reset                           | ☐      |
| Recovered a deleted commit                     | ☐      |
| Understood the differences between reset modes | ☐      |

---

# Outcome

After completing **Phase 05 – Undo Operations**, you will be able to:

* Correct the latest commit using `git commit --amend`.
* Safely undo commits using `git revert`.
* Move `HEAD` with `git reset` in **soft**, **mixed**, and **hard** modes.
* Understand how each reset mode affects the **commit history**, **staging area**, and **working directory**.
* Recover seemingly lost commits using `git reflog`.
