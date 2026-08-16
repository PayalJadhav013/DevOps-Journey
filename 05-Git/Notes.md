# Git Notes

## 1. Introduction to Git

Git is a distributed version control system used to track changes in source code and manage different versions of a project.

Git is commonly used with GitHub in DevOps workflows.

---

## 2. Check Git Version

```bash
git --version
```

Checks the installed Git version.

---

## 3. Create a Git Repository

Create a project directory:

```bash
mkdir gitrepos
cd gitrepos
mkdir titanwork
cd titanwork
```

Initialize Git:

```bash
git init
```

Check hidden Git files:

```bash
ls -a
```

---

## 4. Create Project Files

Create directories:

```bash
mkdir jupyter
mkdir pluto
mkdir nebula
```

Create multiple files:

```bash
touch saturn{1..10}.py
```

Create files inside directories:

```bash
touch jupyter/test1
touch nebula/testter32
touch pluto/taster89
```

---

## 5. Check Git Status

```bash
git status
```

Shows modified, untracked, and staged files.

---

## 6. Git Add

Add all changes:

```bash
git add .
```

Add a specific file:

```bash
git add saturn1.py
```

---

## 7. Git Commit

Create a commit:

```bash
git commit -m "new files committed"
```

A commit saves a snapshot of the staged changes.

---

## 8. Connect Git with GitHub

Add remote repository:

```bash
git remote add origin https://github.com/PayalJadhav013/titanwork.git
```

Check Git configuration:

```bash
cat .git/config
```

Rename branch to main:

```bash
git branch -M main
```

Push the project:

```bash
git push -u origin main
```

---

## 9. Git Log

View commit history:

```bash
git log
```

Short commit history:

```bash
git log --oneline
```

View details of a commit:

```bash
git show ee962e1
```

---

## 10. Git Pull

```bash
git pull
```

Downloads and integrates changes from the remote repository.

---

## 11. Git Branches

Create a branch:

```bash
git branch sprint1
```

List branches:

```bash
git branch -a
```

Switch to a branch:

```bash
git checkout sprint1
```

Modern command:

```bash
git switch sprint1
```

Switch back to main:

```bash
git switch main
```

---

## 12. Work with Branches

Create and modify files in a branch:

```bash
touch jupyter{1..4}.rb
git add .
git commit -m "jupyter changes"
git push origin sprint1
```

Create another branch and add files:

```bash
git switch sprint2
touch sun earth venus mercury
git add .
git commit -m "planets & stars"
git push origin sprint2
```

---

## 13. Git Merge

Switch to the branch where the changes should be merged:

```bash
git switch main
```

Merge another branch:

```bash
git merge sprint1
```

---

## 14. Push All Branches

```bash
git push --all origin
```

Pushes all local branches to the remote repository.

---

## 15. Remove Files

Remove files using Git:

```bash
git rm saturn6.py saturn7.py saturn8.py saturn9.py
```

Rename a tracked file:

```bash
git mv saturn1.py saturn11.py
```

---

## 16. Git Checkout

Check out a file/branch:

```bash
git checkout jupyter1
```

Restore a modified file:

```bash
git checkout -- jupyter1.rb
```

---

## 17. Git Diff

Check unstaged changes:

```bash
git diff
```

Check staged changes:

```bash
git diff --cached
```

Compare with a previous commit:

```bash
git diff 1f1b43f
```

---

## 18. Git Restore

Unstage a file:

```bash
git restore --staged jupyter1.rb
```

Restore a file to its previous tracked state:

```bash
git restore jupyter1.rb
```

---

## 19. Git Revert

```bash
git revert HEAD
```

Creates a new commit that reverses the changes from the previous commit.

---

## 20. Git Reset

Hard reset to a previous commit:

```bash
git reset --hard 1f1b43f
```

This moves the current branch back to that commit and discards working-tree changes.

---

## 21. Git SSH Login

Git can be connected to GitHub using SSH keys instead of entering credentials repeatedly.

Basic workflow:

```text
Generate SSH key
      ↓
Add public key to GitHub
      ↓
Test SSH connection
      ↓
Use SSH repository URL
```

---

## 22. Git Tags

Tags are used to mark important points in Git history, commonly releases.

Example:

```bash
git tag v1.0.0
```

List tags:

```bash
git tag
```

---

## 23. Semantic Versioning

Semantic Versioning commonly follows:

```text
MAJOR.MINOR.PATCH
```

Example:

```text
v1.2.3
```

- **MAJOR** → Breaking changes
- **MINOR** → New backward-compatible features
- **PATCH** → Bug fixes

---

## Important Git Commands Practiced

```bash
git --version
git init
git status
git add .
git commit -m "message"
git remote add origin
git branch
git branch -a
git checkout
git switch
git merge
git push
git pull
git log
git log --oneline
git show
git diff
git restore
git revert
git reset --hard
git rm
git mv
git tag
```

---

## Module Status

**Status:** ✅ Completed

**Topics Completed:** 23