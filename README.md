Here’s a **clear, practical guide to Git commands you’ll use in Visual Studio Code (VS Code)**, with **descriptions and when to use them**.

---

# 🔧 Basic Setup Commands

### 1. Configure Git (first time)

```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
```

👉 Sets your identity for commits.

```bash
git config --list
```

👉 Shows your current Git configuration.

---

# 📁 Repository Commands

### 2. Initialize a repo

```bash
git init
```

👉 Turns your project folder into a Git repository.

### 3. Clone a repo

```bash
git clone <repo-url>
```

👉 Downloads an existing repo (e.g., from GitHub).

---

# 📊 Checking Status

### 4. Check current status

```bash
git status
```

👉 Shows:

* modified files
* staged files
* untracked files

---

# ➕ Adding & Committing

### 5. Add files to staging

```bash
git add filename
```

👉 Add one file

```bash
git add .
```

👉 Add all changes

---

### 6. Commit changes

```bash
git commit -m "Your message"
```

👉 Saves staged changes with a message.

---

# 🔍 Viewing History

### 7. View commit history

```bash
git log
```

```bash
git log --oneline
```

👉 Short version of history

---

# 🔄 Branching

### 8. Create a branch

```bash
git branch branch-name
```

### 9. Switch branch

```bash
git checkout branch-name
```

OR (modern way):

```bash
git switch branch-name
```

---

### 10. Create + switch branch

```bash
git checkout -b branch-name
```

---

### 11. List branches

```bash
git branch
```

---

# 🔀 Merging

### 12. Merge branch

```bash
git merge branch-name
```

👉 Merge another branch into current branch.

---

# 🌐 Remote Repositories

### 13. Add remote

```bash
git remote add origin <repo-url>
```

### 14. View remotes

```bash
git remote -v
```

---

### 15. Push to remote

```bash
git push origin branch-name
```

👉 First push:

```bash
git push -u origin branch-name
```

---

### 16. Pull changes

```bash
git pull origin branch-name
```

👉 Fetch + merge

---

### 17. Fetch changes only

```bash
git fetch
```

👉 Downloads changes without merging.

---

# 🔁 Undo / Fix Mistakes

### 18. Unstage file

```bash
git reset filename
```

---

### 19. Discard changes

```bash
git checkout -- filename
```

---

### 20. Reset commits

```bash
git reset --soft HEAD~1
```

👉 Undo last commit, keep changes

```bash
git reset --hard HEAD~1
```

👉 ⚠️ Deletes last commit completely

---

# 🧹 Cleaning

### 21. Remove untracked files

```bash
git clean -f
```

---

# 🔐 Stashing (temporary save)

### 22. Save work temporarily

```bash
git stash
```

### 23. Restore stash

```bash
git stash pop
```

---

# 🧠 Useful VS Code Git Tips

Inside Visual Studio Code you can:

* Use **Source Control panel** (left sidebar)
* Click **+** to stage files
* Type commit messages directly
* Use built-in buttons for:

  * Push / Pull
  * Branch switching
  * Merge conflict resolution

---

# ⭐ Common Workflow (Real Example)

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin <repo-url>
git push -u origin main
```

---

# 💡 Pro Tips

* Commit often with meaningful messages
* Use branches for features (`feature-login`, etc.)
* Pull before pushing to avoid conflicts
* Use `.gitignore` to exclude unnecessary files

---

If you want, I can give you:

* 🧩 **Git commands cheat sheet PDF style**
* ⚔️ **Merge conflict solving guide**
* 🚀 **Beginner → advanced Git roadmap**

Just tell me 👍
