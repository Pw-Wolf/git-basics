# Git Cheatsheet

## Working Directory | Staging Area | Repository

### Initialize a Git repository
```bash
git init
```

### Display the current state of the repository
```bash
git status
```

### View commit history
```bash
git log
git log --oneline
```

### Change the default Git editor
```bash
git config --global core.editor "code --wait"
```

### Set global email (use `--local` for local settings)
```bash
git config --global user.email <email>
```

### Set global username (use `--local` for local settings)
```bash
git config --global user.name <name>
```

### Modify the last commit
```bash
git commit --amend
```

### Add a file to the staging area
```bash
git add <file-name>
```

### Add all files in the directory to the staging area
```bash
git add .
```

### Commit changes
```bash
git commit -m "<message>"
```

### Stage all changes and commit
```bash
git commit -a -m "<message>"
```

### List all branches
```bash
git branch
```

### Rename a branch
```bash
git branch -m <old-name> <new-name>
```

### Create a new branch
```bash
git branch <branch-name>
```

### Switch to another branch
```bash
git switch <branch-name>
```

### Legacy command for switching branches
```bash
git checkout <branch-name>
```

### Create and switch to a branch
```bash
git switch -c <branch-name>
```

### Delete a branch
```bash
git branch -d <branch-name>
```

### Force delete a branch
```bash
git branch -D <branch-name>
```

### Rename the current branch
```bash
git branch -m <new-branch-name>
```

### Merge a branch into the current one
```bash
git switch master
git merge <branch-name>
```

### Show unstaged changes
```bash
git diff
```

### Show all changes (staged and unstaged)
```bash
git diff <HEAD>
```

### Show staged changes
```bash
git diff --staged
git diff --cached
```

### Show changes for a specific file
```bash
git diff <HEAD> <file-name>
```

### Show differences between two commits
```bash
git diff <commit1>..<commit2>
```

### Show changes between HEAD and its previous commit
```bash
git diff HEAD HEAD~1
```

### Stash changes without committing
```bash
git stash
```

### Apply stashed changes
```bash
git stash pop
```

### Checkout a specific commit (detached HEAD)
```bash
git log --oneline
git checkout <commit-hash>
```

### Checkout a previous commit
```bash
git checkout HEAD~1
```

### Return to the last commit
```bash
git switch <branch-name>
```

### Time-based reference
```bash
git checkout <branch-name>@{2.days.ago}
git checkout <branch-name>@{yesterday}
```

### Discard current changes for a file
```bash
git checkout HEAD <file-name>
git checkout -- <file-name>
```

### Restore changes for a file (alternative to checkout)
```bash
git restore <file-name>
```

### Restore a file from another commit
```bash
git restore --source <commit-hash> <file-name>
```

### Unstage a file
```bash
git restore --staged <file-name>
```

### Reset repository to a commit but keep changes in the working directory
```bash
git reset <commit-hash>
```

### Reset repository and discard working directory changes
```bash
git reset --hard <commit-hash>
```

### Restore a commit using reflog
```bash
git reset --hard master@{1}
```

### Revert a commit
```bash
git revert
```

### Clone a repository
```bash
git clone <repo-url>
```

### Display remote repositories
```bash
git remote -v
```

### Rename a remote
```bash
git remote rename <old-name> <new-name>
```

### Add a remote repository
```bash
git remote add <name> <repository-url>
```

### Remove a remote repository
```bash
git remote remove <name>
```

### Push changes to a remote repository
```bash
git push <remote> <branch>
```

### Specify local and remote branches for push
```bash
git push <remote> <local-branch>:<remote-branch>
```

### Set up tracking between local and remote branches
```bash
git push -u <remote> <branch>
```

### Pull changes (fetch + merge)
```bash
git pull <remote> <branch>
```

### Fetch changes from remote to local repository
```bash
git fetch <remote> <branch>
```

### Rebase changes from another branch
```bash
git rebase <branch>
```

### Allow commit modifications during a rebase
```bash
git rebase -i HEAD~4
```

### List all tags
```bash
git tag
```

### List tags matching a filter
```bash
git tag -l "*beta*"
```

### Checkout a specific tag
```bash
git checkout <tag>
```

### Show differences between two tags
```bash
git diff <tag1> <tag2>
```

### Create a lightweight tag
```bash
git tag <tag-name>
```

### Create an annotated tag
```bash
git tag -a <tag-name>
```

### Create an annotated tag with a message
```bash
git tag -a <tag-name> -m "<message>"
```

### Show commit associated with a tag
```bash
git show <tag>
```

### Tag a specific commit
```bash
git tag <tag-name> <commit>
```

### Force re-tagging a commit
```bash
git tag -f <tag-name> <commit>
```

### Delete a tag
```bash
git tag -d <tag-name>
```

### Push a specific tag to remote
```bash
git push <remote> <tag>
```

### Push all tags to remote
```bash
git push <remote> --tags
```

### Hash content using SHA-1
```bash
echo "hi" | git hash-object --stdin
```

### Hash and save content as an object
```bash
echo "hi" | git hash-object --stdin -w
```

### Display the content of an object
```bash
git cat-file -p <object-hash>
```

### Show detailed local logs
```bash
git reflog show HEAD
```

### Create custom Git aliases
```bash
git config --global alias.<custom-name> <command>
git config --global alias.b branch
git config --global alias.cm "commit -m"
