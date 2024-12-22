# 🛠️ Git Workflow Implementation Guide

## Initial Setup

### 1. Clone & Remote Setup
```bash
# Clone repository
git clone git@github.com:Smartelco/project-name.git

# Check current remotes
git remote -v

# Add upstream remote (if forked)
git remote add upstream git@github.com:Smartelco/project-name.git

# Verify remotes
git remote -v
```

## Daily Development Workflow

### 1. Sync with Latest Changes
```bash
# Switch to develop branch
git checkout develop

# Pull latest changes
git pull origin develop

# Update from upstream (if forked)
git fetch upstream
git merge upstream/develop
```

### 2. Feature Branch Creation
```bash
# Create new feature branch
git checkout -b feature/123-user-auth

# Push branch to remote
git push -u origin feature/123-user-auth
```

### 3. Development Process
```bash
# Check current status
git status

# Stage specific files
git add src/auth/

# Stage all changes
git add .

# Create commit
git commit -m "🚀 feat: Implement basic auth structure #123"

# Push changes
git push origin feature/123-user-auth
```

### 4. Keeping Feature Branch Updated
```bash
# Update develop branch
git checkout develop
git pull origin develop

# Update feature branch
git checkout feature/123-user-auth
git merge develop

# Resolve conflicts if any and push
git push origin feature/123-user-auth
```

## Advanced Git Operations

### 1. Commit Management
```bash
# Amend last commit message
git commit --amend -m "🚀 feat: Better auth implementation #123"

# Add files to last commit
git add forgotten-file.rs
git commit --amend --no-edit

# Push amended commit (force with care!)
git push --force-with-lease origin feature/123-user-auth
```

### 2. History Clean-up
```bash
# Interactive rebase last N commits
git rebase -i HEAD~3

# Squash commits during rebase
# Edit in interactive mode:
pick f7f3f6d feat: Add auth model
squash 310154e feat: Update auth validations
squash a5f4a0d feat: Complete auth implementation

# Force push after rebase
git push --force-with-lease origin feature/123-user-auth
```

### 3. Branch Management
```bash
# List all branches
git branch -a

# Delete local branch
git branch -d feature/123-user-auth

# Delete remote branch
git push origin --delete feature/123-user-auth

# Rename branch
git branch -m old-name new-name
```

## Special Scenarios

### 1. Emergency Hotfix
```bash
# Create hotfix from main
git checkout main
git checkout -b hotfix/789-security-patch

# Make fixes and commit
git commit -m "🐛 fix: Resolve security vulnerability fixes #789"

# Merge to main
git checkout main
git merge hotfix/789-security-patch
git push origin main

# Backport to develop
git checkout develop
git merge hotfix/789-security-patch
git push origin develop
```

### 2. Release Branch
```bash
# Create release branch
git checkout develop
git checkout -b release/1.0.0

# Make release preparations
git commit -m "🚀 chore: Prepare for 1.0.0 release #999"

# Merge to main
git checkout main
git merge release/1.0.0
git tag -a v1.0.0 -m "Version 1.0.0"
git push origin main --tags

# Backport to develop
git checkout develop
git merge release/1.0.0
git push origin develop
```

### 3. Conflict Resolution
```bash
# When merge conflict occurs
git status                    # Check conflicted files
git diff                      # Review differences

# After resolving conflicts
git add <resolved-files>
git commit -m "🔀 chore: Resolve merge conflicts"
git push origin feature/123-user-auth
```

## Useful Git Commands

### 1. Status & History
```bash
# Detailed status
git status -v

# Log with graph
git log --graph --oneline --all

# File history
git log --follow -p -- file.rs

# Branch comparison
git diff branch1..branch2
```

### 2. Temporary Work
```bash
# Stash changes
git stash save "WIP: Authentication implementation"

# List stashes
git stash list

# Apply stash
git stash apply stash@{0}

# Pop stash
git stash pop

# Clear stashes
git stash clear
```

### 3. Recovery Commands
```bash
# Undo last commit (keep changes)
git reset --soft HEAD^

# Discard uncommitted changes
git restore <file>

# Revert commit
git revert <commit-hash>

# Find lost commits
git reflog
```

## Git Configuration Tips

### 1. Useful Aliases
```bash
# Add to ~/.gitconfig
[alias]
    st = status
    co = checkout
    br = branch
    ci = commit
    lg = log --graph --oneline
    unstage = reset HEAD --
    last = log -1 HEAD
```

### 2. Global Settings
```bash
# Set user info
git config --global user.name "Your Name"
git config --global user.email "your.email@smartelco.com"

# Set default branch
git config --global init.defaultBranch main

# Set default pull behavior
git config --global pull.rebase true
```

## Best Practices Reminders

1. **Before Creating Branch**
   ```bash
   git checkout develop
   git pull origin develop
   git checkout -b feature/new-feature
   ```

2. **Before Pushing Changes**
   ```bash
   git fetch origin
   git rebase origin/develop
   git push origin feature/new-feature
   ```

3. **Before Merging**
   ```bash
   git checkout develop
   git pull origin develop
   git merge --no-ff feature/new-feature
   git push origin develop
   ```

4. **After Successful Merge**
   ```bash
   git checkout develop
   git pull origin develop
   git branch -d feature/new-feature
   git push origin --delete feature/new-feature
   ```