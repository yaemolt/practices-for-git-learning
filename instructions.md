# Git Learning Path

## Index
1. [Using Git in VS Code](#using-git-in-vs-code)
    1. [Verify Git Installation](#verify-git-installation)
    2. [Initialize a Git Repository](#initialize-a-git-repository)
    3. [Check File Status](#check-file-status)
    4. [Track New Files](#track-new-files)
    5. [Commit Changes](#commit-changes)
    6. [View Commit History](#view-commit-history)
    7. [Modify Commit History](#modify-commit-history)
    8. [Revert to a Previous Commit](#revert-to-a-previous-commit)
    9. [Ignore Files with .gitignore](#ignore-files-with-gitignore)
2. [Working with GitHub](#working-with-github)
    1. [Push Code to GitHub](#push-code-to-github)
    2. [Pull Changes from GitHub](#pull-changes-from-github)
    3. [Create a New Branch](#create-a-new-branch)

## Using Git in VS Code

1. **Create a New Folder**: Start by creating a directory that will contain your project files.
2. **Create Files in Your Folder**: Add the necessary files into the directory, for example, source code or documentation.

### Verify Git Installation

Before you start using Git, ensure that it's installed properly by checking the version:
```sh
git version
```
This command will display the installed Git version if Git is available on your system.

### Initialize a Git Repository
To begin tracking changes in your project folder, you need to create a local Git repository:
```sh
git init
```
This command will initialize a new `.git` directory within your project folder, which Git will use to store all version history and metadata.

### Check File Status
To see the current status of your files in relation to the repository:
```sh
git status
```
**Output Example**:
```
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        how_to_use_vscode_with_github.md

nothing added to commit but untracked files present (use "git add" to track)
```
This output tells you that Git has detected new files that are not yet tracked. Untracked files are files that haven't been added to the repository's version control.

### Track New Files
To move a file from an "untracked" to a "tracked" state, use the following command:
```sh
git add <filename>
```
For example:
```sh
git add guide.md
```
**Output Example**:
```
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   guide.md
```
The file `guide.md` is now staged, meaning it's ready to be included in the next commit.

### Commit Changes
To save your staged changes, you need to create a commit:
```sh
git commit -m "Descriptive message about the changes"
```
The `-m` flag allows you to include a commit message that describes what was changed, making it easier to understand the history of modifications.

### View Commit History
You can view the history of all commits in your repository using:
1. Detailed view of commits:
```sh
git log
```
This command shows information about each commit, including the commit ID, author, date, and commit message.

**Output Example**:
```
commit 2f296dc9f7f1fa63b1acd406d3c61e182d0afcc3 (HEAD -> master)
Author: Yaemlt <jcd474747@163.com>
Date:   Sun Nov 17 22:47:27 2024 +0800
```
2. Summarized view of commits:
```sh
git log --oneline
```
This command provides a more concise history by showing only the commit ID and the message.

**Output Example**:
```
2f296dc (HEAD -> master) Initial commit with VSCode setup
```

### Modify Commit History
To modify or delete specific commits, you can use the `git log --oneline` command to view commit IDs, then follow up with operations such as deleting commits.

**Output Example**:
```
50adb32 (HEAD -> master) Deleted an unnecessary question mark
d4edec9 Updated commit history viewing instructions
2f296dc Initial commit with VSCode setup
```

### Revert to a Previous Commit
If you need to revert a file to its state in a previous commit, use:
```sh
git checkout <commit_id> -- <filename>
```
To revert the entire repository to an earlier state and discard all subsequent changes, use:
```sh
git reset --hard <commit_id>
```
This command will move your repository back to the specified commit and delete all commits that came after it.

### Ignore Files with `.gitignore`
To specify files that should not be tracked by Git, create a `.gitignore` file in the root directory of your repository. Add file patterns that you want Git to ignore:
```
<filename>
```
For example, to ignore all `.log` files, add:
```
*.log
```

## Working with GitHub

### Push Code to GitHub
If you want to share your local repository on GitHub, first connect it to a remote Git repository:
```sh
git remote add origin https://github.com/username/repository.git
git branch -M main
git push -u origin main
```
- `git remote add origin <url>`: Adds a new remote repository.
- `git branch -M main`: Renames your current branch to `main`.
- `git push -u origin main`: Pushes your local repository to GitHub and sets `origin/main` as the default upstream branch.

### Pull Changes from GitHub
To synchronize your local repository with the changes made in the remote repository:
```sh
git pull
```
This command will fetch the latest changes from GitHub and merge them into your local branch.

### Create a New Branch
To create and switch to a new branch:
```sh
git checkout -b <branchname>
```
This is useful for creating a separate workspace for new features or experimental changes without affecting the main codebase.

