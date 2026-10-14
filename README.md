===Add an image in the README.md file.===

<img width="260" height="220" alt="Screenshot 2026-10-14 132518" src="https://github.com/user-attachments/assets/44126f4e-c700-4634-aed8-4883073a3f06" />


# Lab 2 – Git & GitHub Commands

A walkthrough of the Git commands used in this lab: creating a repo, working with branches, stashing, and tagging.

## Table of Contents

1. [Create a project and push it to a remote repo](#1-create-a-project-and-push-it-to-a-remote-repo)
2. [Create `dev` and `test` branches and push them](#2-create-dev-and-test-branches-and-push-them)
3. [Remove branches locally and remotely](#3-remove-branches-locally-and-remotely)
4. [Switch branches without committing changes](#4-switch-branches-without-committing-changes)
5. [Annotated tags](#5-annotated-tags)

---

## 1. Create a project and push it to a remote repo

Create a new project on your local machine, then push it to the remote repo.

```bash
git init
git remote add origin git@github.com:aya5671/Lab_2.git
git push -u origin main
```

---

## 2. Create `dev` and `test` branches and push them

Create two branches (`dev` and `test`), add one file on each branch, and push the changes to the remote repo.

**Create and push `dev`:**

```bash
git switch -c dev
git add .
git commit -m "dev created"
git push -u origin dev
```

**Create and push `test`:**

```bash
git switch -c test
git add .
git commit -m "test created"
git push -u origin test
```

**Merge `test` into `dev`:**

```bash
git checkout dev
git merge test -m "test merged onto dev"
```

**Merge `dev` into `main` and push:**

```bash
git checkout main
git merge dev -m "dev merged onto main"
git push
```

---

## 3. Remove branches locally and remotely

**Locally:**

```bash
git branch -d test
git branch -d dev
```

**Remotely:**

- On GitHub, click **"View all branches"** and delete each branch manually.

Or from the command line:

```bash
git push origin --delete test
git push origin --delete dev
```

---

## 4. Switch branches without committing changes

Use `git stash` to temporarily save your uncommitted changes, switch branches, and bring the changes back later.

```bash
git stash        # save uncommitted changes
git checkout <branch-name>
git stash pop    # restore the saved changes
```

---

## 5. Annotated tags

**Create an annotated tag (`v1.7`) and push it to the remote:**

```bash
git tag -a v1.7 -m "version 1.7"
git push origin --tags
```

**List tags:**

```bash
git tag -l
```

**Delete a tag locally:**

```bash
git tag -d v1.7
```

**Delete a tag remotely:**

- On GitHub, click **"Tags"** and delete each tag manually.

Or from the command line:

```bash
git push origin --delete v1.7
```

---

## Quick Reference

| Task                     | Command                                  |
| ------------------------ | ---------------------------------------- |
| Initialize a repo        | `git init`                               |
| Add a remote             | `git remote add origin <url>`            |
| Create & switch branch   | `git switch -c <name>`                   |
| Merge a branch           | `git merge <name> -m "<message>"`        |
| Delete local branch      | `git branch -d <name>`                   |
| Delete remote branch     | `git push origin --delete <name>`        |
| Stash / restore changes  | `git stash` / `git stash pop`            |
| Create annotated tag     | `git tag -a <tag> -m "<message>"`        |
| List tags                | `git tag -l`                             |
| Delete local tag         | `git tag -d <tag>`                       |
| Delete remote tag        | `git push origin --delete <tag>`         |


