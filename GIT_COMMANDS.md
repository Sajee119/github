# Full Git & GitHub Command Reference

A complete guide to every Git command you need for daily development — with VS Code integration tips and GitHub workflow patterns.

---

## Table of Contents

- [⚙️ Initial Setup](#️-initial-setup)
- [📁 Repository Management](#-repository-management)
- [📝 Staging & Committing](#-staging--committing)
- [🌿 Branching](#-branching)
- [🔀 Merging & Rebasing](#-merging--rebasing)
- [🌐 Remote Repositories](#-remote-repositories)
- [🏷️ Tags & Releases](#️-tags--releases)
- [🔍 Inspection & Comparison](#-inspection--comparison)
- [↩️ Undoing Changes](#️-undoing-changes)
- [📦 Stashing](#-stashing)
- [🔎 Searching](#-searching)
- [⚡ Advanced Commands](#-advanced-commands)
- [🖥️ VS Code Git Integration](#️-vs-code-git-integration)
- [🔁 GitHub Workflow Patterns](#-github-workflow-patterns)
- [✍️ Commit Message Convention](#️-commit-message-convention)

---

## ⚙️ Initial Setup

```bash
# Set global identity
git config --global user.name "Your Name"
git config --global user.email "you@example.com"

# Set default branch name
git config --global init.defaultBranch main

# Set VS Code as default editor
git config --global core.editor "code --wait"

# Set VS Code as merge/diff tool
git config --global merge.tool vscode
git config --global mergetool.vscode.cmd 'code --wait $MERGED'
git config --global diff.tool vscode
git config --global difftool.vscode.cmd 'code --wait --diff $LOCAL $REMOTE'

# Enable colored output
git config --global color.ui auto

# View all global config
git config --global --list

# Store credentials (HTTPS)
git config --global credential.helper store

# Use SSH key (recommended)
ssh-keygen -t ed25519 -C "you@example.com"
# Then add ~/.ssh/id_ed25519.pub to GitHub → Settings → SSH Keys
```

---

## 📁 Repository Management

```bash
# Initialize a new repository
git init
git init my-project          # init inside new folder

# Clone a repository
git clone https://github.com/user/repo.git
git clone git@github.com:user/repo.git      # via SSH
git clone https://github.com/user/repo.git --depth 1  # shallow clone (faster)
git clone https://github.com/user/repo.git my-folder  # clone into named folder

# Check repository status
git status
git status -s                # short format

# Show repository info
git remote -v                # list remotes
git log --oneline --graph --all  # visual branch graph
```

---

## 📝 Staging & Committing

```bash
# Stage files
git add filename.txt         # stage specific file
git add .                    # stage all changes
git add -p                   # interactively stage hunks (partial file staging)
git add *.js                 # stage all .js files

# Unstage files (keep changes)
git restore --staged filename.txt
git restore --staged .       # unstage everything

# Commit
git commit -m "feat: add login page"
git commit -am "fix: typo"   # stage tracked files + commit in one step
git commit --amend           # edit last commit message (before push)
git commit --amend --no-edit # amend adding staged files without changing message

# Discard working directory changes
git restore filename.txt     # discard changes in file
git restore .                # discard all unstaged changes

# View diff
git diff                     # unstaged changes
git diff --staged            # staged changes (ready to commit)
git diff HEAD                # all uncommitted changes
git diff branch1..branch2    # diff between branches
```

---

## 🌿 Branching

```bash
# List branches
git branch                   # local branches
git branch -r                # remote branches
git branch -a                # all branches

# Create and switch branches
git checkout -b feature/login        # create + switch (classic)
git switch -c feature/login          # create + switch (modern)
git switch main                      # switch to existing branch

# Rename branch
git branch -m old-name new-name
git branch -m new-name               # rename current branch

# Delete branch
git branch -d feature/login          # safe delete (merged only)
git branch -D feature/login          # force delete
git push origin --delete feature/login  # delete remote branch

# Track remote branch
git branch --set-upstream-to=origin/main main
git checkout -b feature/x origin/feature/x  # create local from remote

# List merged / unmerged branches
git branch --merged
git branch --no-merged
```

---

## 🔀 Merging & Rebasing

```bash
# Merge
git merge feature/login              # merge into current branch
git merge --no-ff feature/login      # always create merge commit
git merge --squash feature/login     # squash all commits into one
git merge --abort                    # abort in-progress merge

# Rebase (replay commits on top of another branch)
git rebase main                      # rebase current branch onto main
git rebase -i HEAD~3                 # interactive rebase (squash/edit last 3 commits)
git rebase --abort                   # abort rebase
git rebase --continue                # continue after resolving conflict

# Cherry-pick (apply specific commit)
git cherry-pick abc1234
git cherry-pick abc1234 def5678      # multiple commits
git cherry-pick abc1234 --no-commit  # apply without committing

# Resolve merge conflicts
# 1. Open conflicted files and resolve <<<< ==== >>>> markers
# 2. git add <resolved-file>
# 3. git commit (merge) or git rebase --continue (rebase)
```

---

## 🌐 Remote Repositories

```bash
# Manage remotes
git remote add origin https://github.com/user/repo.git
git remote add upstream https://github.com/original/repo.git
git remote remove origin
git remote rename origin old-origin
git remote set-url origin git@github.com:user/repo.git  # change URL

# Fetch (download without merging)
git fetch origin             # fetch all from origin
git fetch --all              # fetch all remotes
git fetch origin main        # fetch specific branch
git fetch --prune            # remove stale remote-tracking branches

# Pull (fetch + merge/rebase)
git pull                     # pull current branch
git pull origin main         # pull specific remote branch
git pull --rebase            # pull with rebase instead of merge
git pull --rebase=interactive

# Push
git push origin feature/login        # push branch
git push -u origin feature/login     # push + set upstream (first time)
git push --force-with-lease          # safe force push (won't overwrite others' work)
git push origin --tags               # push all tags
git push origin :feature/login       # delete remote branch (old syntax)

# Sync fork with upstream
git fetch upstream
git checkout main
git merge upstream/main
git push origin main
```

---

## 🏷️ Tags & Releases

```bash
# Create tags
git tag v1.0.0                         # lightweight tag
git tag -a v1.0.0 -m "Release v1.0.0" # annotated tag (recommended)
git tag -a v1.0.0 abc1234              # tag a specific commit

# List tags
git tag
git tag -l "v1.*"                      # filter by pattern

# Push tags
git push origin v1.0.0                 # push specific tag
git push origin --tags                 # push all tags

# Delete tags
git tag -d v1.0.0                      # delete local tag
git push origin --delete v1.0.0        # delete remote tag

# Show tag info
git show v1.0.0
```

---

## 🔍 Inspection & Comparison

```bash
# Log
git log                                # full log
git log --oneline                      # compact log
git log --oneline --graph --all        # visual graph
git log --author="Name"                # filter by author
git log --since="2024-01-01"           # filter by date
git log --grep="fix"                   # filter by commit message
git log -p                             # log with diffs
git log --stat                         # log with file change stats
git log main..feature                  # commits in feature not in main
git log -n 10                          # last 10 commits

# Show specific commit
git show abc1234                       # show commit details + diff
git show HEAD                          # show latest commit
git show HEAD~2                        # show 2 commits ago

# Blame (who changed each line)
git blame filename.txt
git blame -L 10,25 filename.txt        # specific lines

# Diff
git diff                               # unstaged vs staged
git diff --staged                      # staged vs last commit
git diff HEAD~1                        # current vs 1 commit ago
git diff v1.0.0..v2.0.0               # between tags
git diff --name-only                   # only file names

# Compare branches
git diff main feature/login            # full diff
git diff main..feature/login --stat    # summary only
```

---

## ↩️ Undoing Changes

```bash
# Undo last commit (keep changes staged)
git reset --soft HEAD~1

# Undo last commit (keep changes unstaged)
git reset --mixed HEAD~1   # (default)

# Undo last commit (discard changes completely)
git reset --hard HEAD~1

# Revert a commit (creates a new undo commit — safe for shared branches)
git revert abc1234
git revert HEAD            # revert last commit

# Remove file from staging area
git restore --staged filename.txt

# Discard working directory changes
git restore filename.txt
git restore .

# Reset file to a specific commit
git checkout abc1234 -- filename.txt

# Remove untracked files
git clean -n               # dry run (show what would be removed)
git clean -f               # remove untracked files
git clean -fd              # remove untracked files and directories
git clean -fdx             # remove including .gitignore'd files
```

---

## 📦 Stashing

```bash
# Stash changes
git stash                              # stash tracked changes
git stash -u                           # include untracked files
git stash save "WIP: login feature"    # stash with description

# List stashes
git stash list

# Apply stash
git stash pop                          # apply latest and remove from stash
git stash apply stash@{2}             # apply specific stash (keep in stash)
git stash drop stash@{0}              # delete specific stash
git stash clear                        # delete all stashes

# Show stash contents
git stash show -p stash@{0}

# Create branch from stash
git stash branch feature/name stash@{0}
```

---

## 🔎 Searching

```bash
# Search in code (all commits)
git grep "function login"              # search working tree
git grep -n "TODO"                     # with line numbers
git grep -l "import React"            # files only

# Search commit history
git log -S "functionName"             # commits that added/removed string (pickaxe)
git log -G "regex.*pattern"           # commits matching regex
git log --all --grep="bug fix"        # search commit messages

# Find which commit introduced a bug (binary search)
git bisect start
git bisect bad                         # current commit is bad
git bisect good v1.2.0                # last known good commit
# Git checks out middle commit; test it, then:
git bisect good   # or: git bisect bad
# Repeat until Git identifies the first bad commit
git bisect reset  # end bisect session
```

---

## ⚡ Advanced Commands

```bash
# Submodules
git submodule add https://github.com/user/lib.git libs/lib
git submodule init
git submodule update --init --recursive
git submodule update --remote          # update to latest remote

# Sparse checkout (check out only part of a repo)
git sparse-checkout init
git sparse-checkout set src/ docs/

# Reflog (recover lost commits)
git reflog                             # list all HEAD movements
git checkout abc1234                   # restore a "lost" commit

# Signing commits with GPG
git config --global commit.gpgsign true
git config --global user.signingkey YOUR_KEY_ID

# Worktrees (multiple checkouts of same repo)
git worktree add ../project-hotfix hotfix/urgent-bug
git worktree list
git worktree remove ../project-hotfix

# Archive repository
git archive --format=zip HEAD > project.zip

# Count contributions
git shortlog -sn                       # commits per author
git shortlog -sn --all                 # including all branches
```

---

## 🖥️ VS Code Git Integration

| Action | Keyboard Shortcut | Description |
|--------|-------------------|-------------|
| Open Source Control | `Ctrl+Shift+G` | View changed files |
| Stage file | Click `+` next to file | Stage individual file |
| Unstage file | Click `-` next to file | Remove from staging |
| Commit | `Ctrl+Enter` in message box | Commit staged changes |
| Open Git Graph | Command Palette → "Git: Graph" | Visual history |
| Resolve conflicts | Click conflict file | Open 3-way merge editor |
| Compare with HEAD | Right-click file → "Open Changes" | Diff view |
| Git Blame | Install GitLens extension | Inline blame annotations |

### Recommended VS Code Extensions for Git
- **GitLens** — Enhanced blame, history, and comparisons
- **Git Graph** — Visual branch graph
- **GitHub Pull Requests** — Manage PRs inside VS Code
- **Git History** — Browse file/line history

---

## 🔁 GitHub Workflow Patterns

### Feature Branch Workflow
```bash
git checkout main && git pull                # start from latest main
git checkout -b feature/my-feature          # create feature branch
# ... develop ...
git add . && git commit -m "feat: ..."
git push -u origin feature/my-feature
# Open Pull Request on GitHub → review → merge → delete branch
git checkout main && git pull               # sync after merge
git branch -d feature/my-feature           # clean up local
```

### Gitflow Workflow
```bash
# main = production, develop = integration
git checkout develop && git pull
git checkout -b feature/x develop
# ... develop ...
git checkout develop && git merge --no-ff feature/x
# When ready to release:
git checkout -b release/1.0.0 develop
git checkout main && git merge --no-ff release/1.0.0
git tag -a v1.0.0 -m "Release 1.0.0"
```

### Hotfix Workflow
```bash
git checkout main && git pull
git checkout -b hotfix/critical-bug
# ... fix ...
git commit -m "fix: critical bug in payment"
git checkout main && git merge --no-ff hotfix/critical-bug
git tag -a v1.0.1 -m "Hotfix 1.0.1"
git checkout develop && git merge --no-ff hotfix/critical-bug
git branch -d hotfix/critical-bug
```

---

## ✍️ Commit Message Convention

Use the **Conventional Commits** specification:

```
<type>(<scope>): <short summary>

[optional body]

[optional footer(s)]
```

### Types
| Type | Description |
|------|-------------|
| `feat` | New feature |
| `fix` | Bug fix |
| `docs` | Documentation only |
| `style` | Formatting, no logic change |
| `refactor` | Code restructure, no feature/fix |
| `perf` | Performance improvement |
| `test` | Adding or fixing tests |
| `chore` | Build process, tool changes |
| `ci` | CI/CD configuration changes |
| `build` | Changes affecting build system |
| `revert` | Reverts a previous commit |

### Examples
```
feat(auth): add OAuth2 Google login
fix(cart): prevent duplicate items on fast click
docs(readme): update installation instructions
refactor(api): extract user service layer
test(checkout): add integration tests for payment flow
chore(deps): upgrade React to v18.3
```

### Breaking Changes
```
feat(api)!: change authentication endpoint path

BREAKING CHANGE: /auth/login moved to /v2/auth/signin
Update all clients to use the new path.
```

---

*Keep commits atomic, branches short-lived, and PRs small. Ship often.*
