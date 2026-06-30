# Phase 04 – GitHub Integration Practice

## Objective

Learn how to connect a local Git repository to GitHub, push and pull changes, fetch updates, clone repositories, and manage remote repositories.

---

# Learning Outcomes

After completing this practice, you will be able to:

* Create a GitHub repository
* Connect a local repository to GitHub
* Add and view remote repositories
* Push local commits to GitHub
* Pull remote changes
* Fetch remote changes
* Clone an existing repository
* Troubleshoot common GitHub integration issues

---

# Prerequisites

Create a local repository.

```bash
mkdir git-phase4-practice

cd git-phase4-practice

git init
```

Create a README.

```bash
echo "# GitHub Integration Practice" > README.md
```

Commit it.

```bash
git add .

git commit -m "Initial commit"
```

---

# Exercise 1 – Create a GitHub Repository

1. Log in to GitHub.
2. Click **New Repository**.
3. Repository Name:

```
git-phase4-practice
```

4. Choose **Public**.
5. Click **Create Repository**.

Do **NOT** initialize with a README because one already exists locally.

---

# Exercise 2 – Add a Remote Repository

Copy the GitHub repository URL.

Using HTTPS:

```bash
git remote add origin https://github.com/<username>/git-phase4-practice.git
```

Using SSH:

```bash
git remote add origin git@github.com:<username>/git-phase4-practice.git
```

Verify.

```bash
git remote
```

Expected Output

```text
origin
```

---

# Exercise 3 – View Remote Details

List remotes.

```bash
git remote -v
```

Expected Output

```text
origin  https://github.com/<username>/git-phase4-practice.git (fetch)

origin  https://github.com/<username>/git-phase4-practice.git (push)
```

View detailed information.

```bash
git remote show origin
```

---

# Exercise 4 – Rename Default Branch

Rename to **main**.

```bash
git branch -M main
```

Verify.

```bash
git branch
```

---

# Exercise 5 – Push to GitHub

First push.

```bash
git push -u origin main
```

Verify.

```bash
git status
```

Expected Output

```text
Your branch is up to date with 'origin/main'.
```

---

# Exercise 6 – Push Another Commit

Modify README.

```bash
echo "GitHub Integration" >> README.md
```

Commit.

```bash
git add .

git commit -m "Update README"
```

Push.

```bash
git push
```

Verify the changes on GitHub.

---

# Exercise 7 – Pull Changes

Edit the README directly on GitHub.

Return to your terminal.

Pull the latest changes.

```bash
git pull
```

Verify.

```bash
git log --oneline
```

---

# Exercise 8 – Fetch Changes

Fetch updates without merging.

```bash
git fetch
```

View downloaded commits.

```bash
git log HEAD..origin/main --oneline
```

Merge manually.

```bash
git merge origin/main
```

---

# Exercise 9 – Clone a Repository

Go outside the project.

```bash
cd ..
```

Clone the repository.

HTTPS

```bash
git clone https://github.com/<username>/git-phase4-practice.git
```

or

SSH

```bash
git clone git@github.com:<username>/git-phase4-practice.git
```

Move inside.

```bash
cd git-phase4-practice
```

Verify.

```bash
git remote -v
```

---

# Exercise 10 – Add Another Remote

Create another repository.

Example:

```
git-backup
```

Add it.

```bash
git remote add backup https://github.com/<username>/git-backup.git
```

Verify.

```bash
git remote -v
```

---

# Exercise 11 – Remove and Re-add a Remote

Remove.

```bash
git remote remove backup
```

Verify.

```bash
git remote
```

Re-add.

```bash
git remote add backup https://github.com/<username>/git-backup.git
```

---

# Exercise 12 – Complete GitHub Workflow

```bash
git add .

git commit -m "Final update"

git push

git pull

git fetch

git remote -v

git log --oneline
```

---

# Mini Challenge

Complete the following without looking at the notes:

* Create a GitHub repository.
* Connect your local repository.
* Rename the branch to `main`.
* Push your code.
* Make another commit.
* Push again.
* Edit a file on GitHub.
* Pull the changes.
* Fetch remote updates.
* Clone the repository.
* Add another remote.
* Remove the remote.

---

# Expected Repository Structure

```text
git-phase4-practice/
│
├── .git/
├── README.md
└── app.py
```

---

# Common Commands

| Command                       | Description                         |
| ----------------------------- | ----------------------------------- |
| `git remote add origin <url>` | Add a remote repository             |
| `git remote`                  | List remote names                   |
| `git remote -v`               | Show remote URLs                    |
| `git remote show origin`      | Show remote details                 |
| `git remote remove origin`    | Remove a remote                     |
| `git branch -M main`          | Rename the current branch to `main` |
| `git push -u origin main`     | First push and set upstream         |
| `git push`                    | Push changes                        |
| `git pull`                    | Fetch and merge remote changes      |
| `git pull origin main`        | Pull a specific branch              |
| `git fetch`                   | Download remote changes             |
| `git fetch origin`            | Fetch from a specific remote        |
| `git merge origin/main`       | Merge fetched changes               |
| `git clone <url>`             | Clone a repository                  |

---

# Self-Assessment Checklist

| Task                         | Status |
| ---------------------------- | ------ |
| Created a GitHub repository  | ☐      |
| Added a remote               | ☐      |
| Verified remotes             | ☐      |
| Renamed the branch to `main` | ☐      |
| Pushed code to GitHub        | ☐      |
| Pulled changes               | ☐      |
| Fetched remote changes       | ☐      |
| Cloned a repository          | ☐      |
| Added a second remote        | ☐      |
| Removed a remote             | ☐      |

---

# Outcome

After completing **Phase 04 – GitHub Integration**, you will be able to:

* Connect local repositories to GitHub.
* Manage remote repositories.
* Push and pull changes confidently.
* Fetch updates without merging.
* Clone repositories for collaboration.
* Work effectively with remote repositories in real-world projects.
