# Phase 02 – Working with Changes Practice

## Objective

Learn how to inspect, stage, restore, rename, and remove files while working with Git.

---

# Learning Outcomes

After completing this practice, you will be able to:

* Modify tracked files
* View unstaged changes
* View staged changes
* Remove tracked files
* Rename files using Git
* Restore modified files
* Unstage files safely

---

# Prerequisites

Create a practice repository.

```bash
mkdir git-phase2-practice

cd git-phase2-practice

git init
```

Create a file.

```bash
echo "Hello Git" > app.py
```

Commit it.

```bash
git add .

git commit -m "Initial commit"
```

---

# Exercise 1 – Modify a File

Append a new line.

```bash
echo "print('Git Phase 2')" >> app.py
```

Check status.

```bash
git status
```

**Expected Output**

```
modified: app.py
```

---

# Exercise 2 – View Unstaged Changes

```bash
git diff
```

View a specific file.

```bash
git diff app.py
```

---

# Exercise 3 – Stage Changes

```bash
git add app.py
```

Verify.

```bash
git status
```

---

# Exercise 4 – View Staged Changes

```bash
git diff --staged
```

or

```bash
git diff --cached
```

---

# Exercise 5 – Unstage the File

```bash
git restore --staged app.py
```

Verify.

```bash
git status
```

The file should remain modified but no longer staged.

---

# Exercise 6 – Restore the File

Discard local changes.

```bash
git restore app.py
```

Verify.

```bash
git status
```

Working tree should be clean.

---

# Exercise 7 – Create Another File

```bash
echo "Notes" > notes.txt
```

Stage and commit.

```bash
git add .

git commit -m "Add notes file"
```

---

# Exercise 8 – Rename a File

Rename using Git.

```bash
git mv notes.txt README.md
```

Check status.

```bash
git status
```

Commit.

```bash
git commit -m "Rename notes.txt to README.md"
```

---

# Exercise 9 – Remove a File

Delete the file.

```bash
git rm README.md
```

Commit.

```bash
git commit -m "Remove README.md"
```

---

# Exercise 10 – Remove from Git Only

Create a file.

```bash
echo "password=123456" > secrets.txt
```

Stage it.

```bash
git add secrets.txt

git commit -m "Add secrets file"
```

Stop tracking the file.

```bash
git rm --cached secrets.txt
```

Verify.

```bash
git status
```

Commit.

```bash
git commit -m "Stop tracking secrets.txt"
```

---

# Exercise 11 – Restore Multiple Files

Create two files.

```bash
echo "A" > file1.txt

echo "B" > file2.txt
```

Modify them.

```bash
echo "New Line" >> file1.txt

echo "New Line" >> file2.txt
```

Restore both.

```bash
git restore file1.txt file2.txt
```

---

# Exercise 12 – Restore Everything

Modify several files.

Restore all.

```bash
git restore .
```

---

# Mini Challenge

Complete the following tasks without looking at the notes:

* Modify a tracked file.
* View unstaged changes.
* Stage the file.
* View staged changes.
* Unstage the file.
* Restore the file.
* Create a new file.
* Rename it using Git.
* Delete it using Git.
* Stop tracking a file while keeping it locally.

---

# Expected Repository Structure

```text
git-phase2-practice/
│
├── .git/
├── app.py
├── secrets.txt
├── file1.txt
└── file2.txt
```

---

# Common Commands

| Command                       | Description                              |
| ----------------------------- | ---------------------------------------- |
| `git status`                  | Show repository status                   |
| `git diff`                    | Show unstaged changes                    |
| `git diff app.py`             | Compare a specific file                  |
| `git diff --staged`           | Show staged changes                      |
| `git diff --cached`           | Same as `--staged`                       |
| `git add <file>`              | Stage a file                             |
| `git restore <file>`          | Discard local changes                    |
| `git restore .`               | Restore all modified files               |
| `git restore --staged <file>` | Unstage a file                           |
| `git restore --staged .`      | Unstage all files                        |
| `git mv old new`              | Rename or move a file                    |
| `git rm <file>`               | Delete a tracked file                    |
| `git rm --cached <file>`      | Stop tracking a file but keep it locally |

---

# Self-Assessment Checklist

| Task                    | Status |
| ----------------------- | ------ |
| Modified a tracked file | ☐      |
| Viewed unstaged changes | ☐      |
| Viewed staged changes   | ☐      |
| Staged a file           | ☐      |
| Unstaged a file         | ☐      |
| Restored a file         | ☐      |
| Renamed a file          | ☐      |
| Deleted a file          | ☐      |
| Stopped tracking a file | ☐      |

---

# Outcome

After completing **Phase 02 – Working with Changes**, you will be able to:

* Inspect changes before committing.
* Understand the difference between staged and unstaged changes.
* Restore unwanted modifications.
* Rename files while preserving Git history.
* Remove files safely.
* Manage the staging area confidently.
