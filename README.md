# Git and GitHub Learning Documentation

## Overview

This document summarizes the key concepts and commands I learned about **Git** and **GitHub**, two essential tools for version control and collaboration in software development.

---

## What is Git?

Git is a distributed version control system (DVCS) that tracks changes in files and facilitates collaboration among developers. It allows:

- **Version tracking**: Maintains a history of changes to the codebase.
- **Branching and merging**: Enables parallel development and seamless integration.
- **Distributed repositories**: Every user has a complete copy of the project.

### Why Use Git?

- **Collaboration**: Work with teams efficiently without overwriting each other’s changes.
- **Backup**: Acts as a reliable backup with full version history.
- **Rollback**: Revert to earlier versions of files in case of errors.

---

## What is GitHub?

GitHub is a cloud-based platform that hosts Git repositories. It provides:

- Remote repositories for sharing and collaboration.
- Tools for pull requests, issue tracking, and project management.
- Integrations with CI/CD tools for automated workflows.

---

## Key Git Commands

### Setup

- `git config --global user.name "Your Name"`: Set your username.
- `git config --global user.email "youremail@example.com"`: Set your email.

### Repository Initialization

- `git init`: Initialize a new Git repository locally.
- `git clone <repository-url>`: Clone an existing repository.

### Staging and Committing Changes

- `git add <file>`: Stage changes for commit.
- `git commit -m "Commit message"`: Commit changes with a message.

### Branching and Merging

- `git branch`: List all branches.
- `git branch <branch-name>`: Create a new branch.
- `git checkout <branch-name>`: Switch to a specific branch.
- `git merge <branch-name>`: Merge changes from another branch.

### Remote Repositories

- `git remote add origin <repository-url>`: Link a local repo to a remote repository.
- `git pull`: Fetch and merge changes from the remote repository.
- `git push`: Push local changes to the remote repository.

# Git Commands Cheat Sheet

A comprehensive reference guide for commonly used Git commands.

## Getting Started

### Initial Setup

```bash
git init                    # Initialize a new Git repository
git clone [url]            # Clone a repository from a remote source
git config --global user.name "[name]"    # Set your username
git config --global user.email "[email]"  # Set your email
```

## Basic Commands

### Status and Information

```bash
git status                 # Check the status of your working directory
git log                    # View commit history
git log --oneline         # View commit history in compact format
git diff                  # Show changes between working directory and staging
git diff --staged        # Show changes between staging and last commit
```

### Basic Workflow

```bash
git add [file]            # Add a file to staging area
git add .                 # Add all changed files to staging area
git commit -m "[message]" # Commit staged changes with a message
git commit -am "[message]"# Add modified files and commit in one step
```

## Branch Operations

### Managing Branches

```bash
git branch                # List all local branches
git branch -a            # List all branches (local and remote)
git branch [name]        # Create a new branch
git branch -d [name]     # Delete a branch
git branch -D [name]     # Force delete a branch
```

### Switching Branches

```bash
git checkout [branch]     # Switch to a branch
git checkout -b [branch]  # Create and switch to a new branch
git switch [branch]       # Switch to a branch (new Git syntax)
git switch -c [branch]    # Create and switch to a new branch (new Git syntax)
```

## Remote Operations

### Managing Remotes

```bash
git remote -v            # List all remote repositories
git remote add [name] [url]  # Add a remote repository
git remote remove [name]     # Remove a remote
```

### Syncing with Remote

```bash
git fetch               # Download objects and refs from remote
git pull               # Fetch and merge changes from remote
git push               # Push local changes to remote
git push -u origin [branch]  # Push branch and set upstream
```

## Advanced Operations

### Merging and Rebasing

```bash
git merge [branch]      # Merge a branch into current branch
git rebase [branch]     # Rebase current branch onto another
git merge --abort       # Abort a merge in case of conflicts
```

### Stashing Changes

```bash
git stash              # Temporarily store modified files
git stash pop          # Apply and remove stashed changes
git stash list         # List all stashed changes
git stash drop         # Delete stashed changes
```

### History Modification

```bash
git reset [file]       # Unstage a file
git reset --soft HEAD~1    # Undo last commit, keep changes staged
git reset --hard HEAD~1    # Undo last commit and all changes
git revert [commit]    # Create new commit that undoes specified commit
```

### Inspection and Comparison

```bash
git show [commit]      # Show commit details
git blame [file]       # Show who changed what and when in a file
git tag               # List all tags
git tag [name]        # Create a new tag
```

## Tips and Tricks

### Aliases and Configuration

```bash
git config --global alias.co checkout    # Create checkout alias
git config --global alias.br branch      # Create branch alias
git config --global alias.ci commit      # Create commit alias
git config --global alias.st status      # Create status alias
```

### Helpful Commands

```bash
git help [command]     # Get help for a Git command
git clean -n          # Show which files would be removed
git clean -f          # Remove untracked files
git reflog            # Show history of HEAD changes
```

## Best Practices

1. Write clear, concise commit messages
2. Commit early and often
3. Don't commit generated files
4. Create a good `.gitignore` file
5. Use branches for new features
6. Pull before pushing
7. Review changes before committing

## Common Issues and Solutions

### Fixing Last Commit Message

```bash
git commit --amend -m "New message"   # Change last commit message
```

### Recovering Lost Changes

```bash
git reflog                # Show history of HEAD changes
git checkout [commit]     # Restore to specific commit
```

### Removing Sensitive Data

```bash
git filter-branch --force --index-filter \
'git rm --cached --ignore-unmatch [file]' HEAD   # Remove sensitive file from history
```

---

Remember to always be careful with commands that modify history (`reset`, `rebase`, `filter-branch`) as they can affect other developers if used on shared branches.

For more detailed information, consult the [official Git documentation](https://git-scm.com/doc).

Please be tuned in into this page for more information on Version Control Systems.
