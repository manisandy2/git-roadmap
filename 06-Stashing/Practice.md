# Phase 06 – Stashing Practice

## Objective

Learn how to temporarily save your uncommitted changes using Git Stash so you can switch tasks without creating unnecessary commits.

---

# Learning Outcomes

After completing this practice, you will be able to:

* Create a stash
* Create a named stash
* Include untracked files in a stash
* List all stashes
* Apply a stash
* Pop a stash
* Drop a stash
* Clear all stashes
* Work with multiple stashes

---

# Prerequisites

Create a practice repository.

```bash
mkdir git-phase6-practice

cd git-phase6-practice

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

# Exercise 1 – Modify a File

Append a new line.

```bash
echo "Version 2" >> app.py
```

Verify.

```bash
git status
```

Expected Output

```text
modified: app.py
```

---

# Exercise 2 – Create Your First Stash

Temporarily save your work.

```bash
git stash
```

Verify.

```bash
git status
```

Expected Output

```text
nothing to commit, working tree clean
```

View the stash.

```bash
git stash list
```

Expected Output

```text
stash@{0}: WIP on main
```

---

# Exercise 3 – Restore a Stash

Apply the latest stash.

```bash
git stash apply
```

Verify.

```bash
git status
```

Notice that the stash still exists.

```bash
git stash list
```

---

# Exercise 4 – Pop a Stash

Create another stash.

```bash
git stash
```

Restore and remove it.

```bash
git stash pop
```

Verify.

```bash
git stash list
```

The applied stash has been removed.

---

# Exercise 5 – Create a Named Stash

Modify the file.

```bash
echo "Login Feature" >> app.py
```

Create a named stash.

```bash
git stash push -m "Login Feature"
```

View.

```bash
git stash list
```

Expected Output

```text
stash@{0}: On main: Login Feature
```

---

# Exercise 6 – Stash Untracked Files

Create a new file.

```bash
echo "Temporary Notes" > notes.txt
```

Verify.

```bash
git status
```

Create a stash including untracked files.

```bash
git stash -u
```

or

```bash
git stash --include-untracked
```

Verify.

```bash
git status
```

---

# Exercise 7 – Stash Ignored Files

Create an ignored file.

```bash
echo "*.log" > .gitignore

touch app.log
```

Stash everything.

```bash
git stash -a
```

or

```bash
git stash --all
```

---

# Exercise 8 – Work with Multiple Stashes

Create the first stash.

```bash
echo "Feature A" >> app.py

git stash push -m "Feature A"
```

Create another stash.

```bash
echo "Feature B" >> app.py

git stash push -m "Feature B"
```

View all stashes.

```bash
git stash list
```

Expected Output

```text
stash@{0}: Feature B

stash@{1}: Feature A
```

Apply the older stash.

```bash
git stash apply stash@{1}
```

---

# Exercise 9 – Drop a Stash

View stashes.

```bash
git stash list
```

Delete one stash.

```bash
git stash drop stash@{1}
```

Verify.

```bash
git stash list
```

---

# Exercise 10 – Clear All Stashes

Delete every stash.

```bash
git stash clear
```

Verify.

```bash
git stash list
```

Expected Output

```text
(no stashes)
```

---

# Exercise 11 – Real-World Workflow

Modify your project.

```bash
echo "Login API" >> app.py
```

Stash your work.

```bash
git stash push -m "Login API"
```

Create a bug-fix branch.

```bash
git switch -c bugfix
```

Fix the bug.

```bash
echo "Bug Fixed" >> app.py

git add .

git commit -m "Fix login bug"
```

Return to the main branch.

```bash
git switch main
```

Restore your work.

```bash
git stash pop
```

---

# Exercise 12 – Complete Practice

```bash
echo "Feature C" >> app.py

git stash push -m "Feature C"

git stash list

git stash apply

git stash pop

git stash drop stash@{0}

git stash clear
```

---

# Mini Challenge

Complete the following without looking at the notes:

* Modify a file.
* Create a stash.
* Create a named stash.
* Create a stash including untracked files.
* List all stashes.
* Apply a specific stash.
* Pop a stash.
* Delete one stash.
* Clear every stash.
* Switch branches while using stashes.

---

# Expected Repository Structure

```text
git-phase6-practice/
│
├── .git/
├── .gitignore
├── README.md
├── app.py
└── notes.txt
```

---

# Common Commands

| Command                         | Description                                  |
| ------------------------------- | -------------------------------------------- |
| `git stash`                     | Stash tracked changes                        |
| `git stash push -m "message"`   | Create a named stash                         |
| `git stash -u`                  | Include untracked files                      |
| `git stash --include-untracked` | Same as `-u`                                 |
| `git stash -a`                  | Include ignored and untracked files          |
| `git stash --all`               | Same as `-a`                                 |
| `git stash list`                | Show all stashes                             |
| `git stash apply`               | Restore the latest stash without removing it |
| `git stash apply stash@{n}`     | Restore a specific stash                     |
| `git stash pop`                 | Restore and remove the latest stash          |
| `git stash drop stash@{n}`      | Delete a specific stash                      |
| `git stash clear`               | Delete all stashes                           |

---

# Self-Assessment Checklist

| Task                                  | Status |
| ------------------------------------- | ------ |
| Created a stash                       | ☐      |
| Created a named stash                 | ☐      |
| Stashed untracked files               | ☐      |
| Listed stashes                        | ☐      |
| Applied a stash                       | ☐      |
| Popped a stash                        | ☐      |
| Deleted a stash                       | ☐      |
| Cleared all stashes                   | ☐      |
| Used stashing during branch switching | ☐      |

---

# Outcome

After completing **Phase 06 – Stashing**, you will be able to:

* Temporarily save unfinished work without committing it.
* Manage multiple stashes efficiently.
* Restore work using **`git stash apply`** or **`git stash pop`**.
* Remove obsolete stashes.
* Switch between tasks or branches without losing changes.
* Use Git Stash effectively in real-world development workflows.
