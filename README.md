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
