# GIT Cheatsheet: Working with Working Directory, Staging Area, and Repository

## Basic Commands
- **Initialize a new Git repository**
  ```bash
  git init
  ```
- **Check the current status of the repository**
  ```bash
  git status
  ```
- **View commit history**
  ```bash
  git log
  git log --oneline
  ```
- **Change the default editor for Git**
  ```bash
  git config --global core.editor "code --wait"
  ```

## Adding and Committing
- **Add a file to the staging area**
  ```bash
  git add <file-name>
  ```
- **Add all files in the current directory to the staging area**
  ```bash
  git add .
  ```
- **Create a commit with a message**
  ```bash
  git commit -m "<commit-message>"
  ```
- **Add and commit in one step**
  ```bash
  git commit -a -m "<commit-message>"
  ```
- **Amend the previous commit**
  ```bash
  git commit --amend
  ```

## Branches
- **List all branches**
  ```bash
  git branch
  ```
- **Create a new branch**
  ```bash
  git branch <branch-name>
  ```
- **Switch to another branch**
  ```bash
  git switch <branch-name>
  ```
  - *Old command:* `git checkout <branch-name>`
- **Create and switch to a new branch**
  ```bash
  git switch -c <branch-name>
  ```
- **Delete a branch**
  - Soft delete:  
    ```bash
    git branch -d <branch-name>
    ```
  - Force delete:  
    ```bash
    git branch -D <branch-name>
    ```
- **Rename a branch**
  ```bash
  git branch -m <old-name> <new-name>
  ```

## Merging Branches
- **Merge a branch into the current branch**
  ```bash
  git switch master
  git merge <branch-name>
  ```

## Differences (Diff)
- **Show changes not yet staged**
  ```bash
  git diff
  ```
- **Show the difference between HEAD and current changes (staged and unstaged)**
  ```bash
  git diff HEAD
  ```
- **Show staged changes**
  ```bash
  git diff --staged
  git diff --cached
  ```
- **Show differences in a specific file**
  ```bash
  git diff HEAD <file-name>
  ```
- **Show differences between two commits**
  ```bash
  git diff <commit-1>..<commit-2>
  ```
- **Difference between HEAD and the previous commit**
  ```bash
  git diff HEAD HEAD~1
  ```

## Temporary Saving (Stash)
- **Stash changes without committing**
  ```bash
  git stash
  ```
- **Apply stashed changes**
  ```bash
  git stash pop
  ```

## Resetting Changes
- **Discard current changes**
  ```bash
  git restore <file-name>
  ```
  - *Old command:* `git checkout -- <file-name>`
- **Restore changes from another commit**
  ```bash
  git restore --source <commit-hash> <file-name>
  ```
- **Unstage a file**
  ```bash
  git restore --staged <file-name>
  ```
- **Reset to a specific commit**
  - Keep changes in the working directory:
    ```bash
    git reset <commit-hash>
    ```
  - Discard all changes:
    ```bash
    git reset --hard <commit-hash>
    ```

## Reverting Changes
- **Revert a specific commit**
  ```bash
  git revert <commit-hash>
  ```

## Remote Repositories
- **Clone a remote repository**
  ```bash
  git clone <repo-url>
  ```
- **Show remote destinations**
  ```bash
  git remote -v
  ```
- **Rename a remote destination**
  ```bash
  git remote rename <old-name> <new-name>
  ```
- **Remove a remote destination**
  ```bash
  git remote remove <name>
  ```
- **Push changes to a remote repository**
  ```bash
  git push <remote> <branch>
  ```
- **Set upstream for a branch**
  ```bash
  git push -u <remote> <branch>
  ```
- **Pull changes from a remote repository**
  ```bash
  git pull <remote> <branch>
  ```
- **Fetch changes without merging**
  ```bash
  git fetch <remote> <branch>
  ```

