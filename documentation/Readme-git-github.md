Git and GitHub
Git:
A distributed version control system.
Manages and tracks changes in your source code during development.
Works locally on your machine without needing an internet connection. Enables features like branching, merging, and version tracking.

GitHub:
A cloud-based platform that hosts Git repositories.
Provides a web interface for managing Git repositories, collaborating with others, and reviewing code.
Offers additional features like pull requests, issues, and project
management tools.
Requires an internet connection to interact with.

# Git Command Reference

This document provides an overview of essential Git commands along with their descriptions and example usage.

## Table of Contents
- [Git Command Reference](#git-command-reference)
  - [Table of Contents](#table-of-contents)
    - [Repository Setup and Configuration](#repository-setup-and-configuration)
    - [Basic Snapshotting](#basic-snapshotting)
    - [Branching and Merging](#branching-and-merging)
    - [Synchronizing with Remote Repositories](#synchronizing-with-remote-repositories)
    - [Pulling and Pushing Locally and Remotely](#pulling-and-pushing-locally-and-remotely)
    - [Undoing Changes](#undoing-changes)
    - [Stashing](#stashing)
    - [Viewing and Exploring History](#viewing-and-exploring-history)
    - [Tagging](#tagging)
    - [Advanced and Collaboration](#advanced-and-collaboration)
    - [Miscellaneous](#miscellaneous)

---

### Repository Setup and Configuration

| Command                                      | Description                                                         | Example Usage                                                 |
|----------------------------------------------|---------------------------------------------------------------------|---------------------------------------------------------------|
| `git init`                                   | Initializes a new Git repository in the current directory.           | `git init`                                                    |
| `git clone <repository_url>`                 | Clones a remote repository to your local machine.                    | `git clone https://github.com/user/repo.git`                  |
| `git config --global user.name "<name>"`     | Sets the global username for Git commits.                            | `git config --global user.name "John Doe"`                    |
| `git config --global user.email "<email>"`   | Sets the global email for Git commits.                               | `git config --global user.email "johndoe@example.com"`        |
| `git remote add origin <url>`                | Adds a remote repository to your project.                            | `git remote add origin https://github.com/user/repo.git`      |

### Basic Snapshotting

| Command                                      | Description                                                         | Example Usage                                                 |
|----------------------------------------------|---------------------------------------------------------------------|---------------------------------------------------------------|
| `git add <file_or_folder>`                   | Adds files or folders to the staging area.                           | `git add .` (adds all files)                                  |
| `git commit -m "<message>"`                  | Records a snapshot of the staged changes.                            | `git commit -m "Initial commit"`                              |
| `git commit --amend -m "<new_message>"`      | Modifies the message of the most recent commit.                      | `git commit --amend -m "Updated commit message"`              |

### Branching and Merging

| Command                                      | Description                                                         | Example Usage                                                 |
|----------------------------------------------|---------------------------------------------------------------------|---------------------------------------------------------------|
| `git branch`                                 | Lists all branches in the repository.                                | `git branch`                                                  |
| `git branch <branch_name>`                   | Creates a new branch.                                                | `git branch feature-branch`                                   |
| `git checkout <branch_name>`                 | Switches to the specified branch.                                    | `git checkout feature-branch`                                 |
| `git checkout -b <branch_name>`              | Creates and switches to a new branch.                                | `git checkout -b feature-branch`                              |
| `git merge <branch_name>`                    | Merges the specified branch into the current branch.                 | `git merge feature-branch`                                    |
| `git rebase <branch_name>`                   | Reapplies commits on top of another base branch.                     | `git rebase main`                                             |
| `git branch -d <branch_name>`                | Deletes a branch (only if it has been merged).                       | `git branch -d feature-branch`                                |

### Synchronizing with Remote Repositories

| Command                                      | Description                                                         | Example Usage                                                 |
|----------------------------------------------|---------------------------------------------------------------------|---------------------------------------------------------------|
| `git fetch`                                  | Downloads objects and refs from another repository.                  | `git fetch origin`                                            |
| `git pull origin <branch>`                   | Fetches and integrates changes from the remote branch.               | `git pull origin main`                                        |
| `git push origin <branch>`                   | Pushes commits from your local branch to the remote branch.          | `git push origin main`                                        |

### Pulling and Pushing Locally and Remotely

| Command                                      | Description                                                         | Example Usage                                                 |
|----------------------------------------------|---------------------------------------------------------------------|---------------------------------------------------------------|
| `git pull origin <branch>`                   | Pulls updates from the remote branch to your local branch.           | `git pull origin main`                                        |
| `git push origin <branch>`                   | Pushes your local commits to the remote branch.                      | `git push origin main`                                        |
| `git push origin <branch> --force`           | Force-pushes your local branch to overwrite the remote branch.       | `git push origin main --force`                                |
| `git pull <remote_name> <branch>`            | Pulls from a specified remote repository using SSH key authentication. | `git pull origin main` (when SSH key is set up)              |
| `git push <remote_name> <branch>`            | Pushes commits to a specified remote branch using SSH key authentication. | `git push origin main` (when SSH key is set up)          |
| `ssh-add <private_key>`                      | Adds your SSH key to the SSH agent for secure access.                | `ssh-add ~/.ssh/id_rsa`                                       |

### Undoing Changes

| Command                                      | Description                                                         | Example Usage                                                 |
|----------------------------------------------|---------------------------------------------------------------------|---------------------------------------------------------------|
| `git revert <commit_hash>`                   | Reverts the specified commit, creating a new commit that undoes it.  | `git revert a1b2c3d`                                          |
| `git reset --soft <commit_hash>`             | Resets the commit history but keeps the changes staged.              | `git reset --soft a1b2c3d`                                    |
| `git reset --hard <commit_hash>`             | Resets the commit history and discards all changes.                  | `git reset --hard a1b2c3d`                                    |
| `git reset HEAD <file>`                      | Unstages a file while keeping the changes in the working directory.  | `git reset HEAD index.html`                                   |
| `git clean -f`                               | Removes untracked files from the working directory.                  | `git clean -f`                                                |

### Stashing

| Command                                      | Description                                                         | Example Usage                                                 |
|----------------------------------------------|---------------------------------------------------------------------|---------------------------------------------------------------|
| `git stash`                                  | Temporarily saves your changes without committing them.              | `git stash`                                                   |
| `git stash pop`                              | Applies stashed changes and removes them from the stash list.        | `git stash pop`                                               |
| `git stash list`                             | Lists all stashed changes.                                           | `git stash list`                                              |

### Viewing and Exploring History

| Command                                      | Description                                                         | Example Usage                                                 |
|----------------------------------------------|---------------------------------------------------------------------|---------------------------------------------------------------|
| `git log`                                    | Shows the commit history for the current branch.                     | `git log`                                                     |
| `git log --oneline`                          | Shows a condensed commit history.                                    | `git log --oneline`                                           |
| `git show <commit_hash>`                     | Displays detailed information about a specific commit.               | `git show a1b2c3d`                                            |
| `git diff`                                   | Shows changes between commits, branches, or your working directory.  | `git diff`                                                    |
| `git diff <branch_name>`                     | Compares changes between the current branch and another branch.       | `git diff main`                                               |

### Tagging

| Command                                      | Description                                                         | Example Usage                                                 |
|----------------------------------------------|---------------------------------------------------------------------|---------------------------------------------------------------|
| `git tag <tag_name>`                         | Creates a lightweight tag at the current commit.                     | `git tag v1.0.0`                                              |
| `git tag -a <tag_name> -m "<message>"`       | Creates an annotated tag with a message.                             | `git tag -a v1.0.0 -m "Release version 1.0.0"`                |
| `git push origin --tags`                     | Pushes all tags to the remote repository.                            | `git push origin --tags`                                      |

### Advanced and Collaboration

| Command                                      | Description                                                         | Example Usage                                                 |
|----------------------------------------------|---------------------------------------------------------------------|---------------------------------------------------------------|
| `git cherry-pick <commit_hash>`              | Applies the changes introduced by a specific commit to the current branch. | `git cherry-pick a1b2c3d`                                     |
| `git rebase -i <base>`                       | Interactively rebase commits to edit, combine, or reorder them.      | `git rebase -i HEAD~3`                                        |
| `git bisect start`                           | Initiates a binary search to find a bug-causing commit.              | `git bisect start`                                            |
| `git bisect bad <commit>`                    | Marks a commit as bad (used during bisecting).                       | `git bisect bad`                                              |
| `git bisect good <commit>`                   | Marks a commit as good (used during bisecting).                      | `git bisect good`                                             |

### Miscellaneous

| Command                                      | Description                                                         | Example Usage                                                 |
|----------------------------------------------|---------------------------------------------------------------------|---------------------------------------------------------------|
| `git blame <file>`                           | Shows who changed what in a file and when.                           | `git blame index.html`                                        |
| `git shortlog`                               | Summarizes commits by author.                                        | `git shortlog -sn`                                            |
| `git archive --format=zip HEAD > archive.zip`| Creates a zip archive of the current branch.                         | `git archive --format=zip HEAD > archive.zip`                 |
| `git gc`                                     | Cleans up unnecessary files and optimizes the repository.            | `git gc`                                                      |
| `git fsck`                                   | Verifies the integrity of the repository.                            | `git fsck`                                                    |
