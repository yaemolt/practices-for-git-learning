# Git 学习路径

## 索引
1. [在 VS Code 中使用 Git](#在-vs-code-中使用-git)
    1. [验证 Git 安装](#验证-git-安装)
    2. [初始化 Git 仓库](#初始化-git-仓库)
    3. [查看文件状态](#查看文件状态)
    4. [追踪新文件](#追踪新文件)
    5. [提交更改](#提交更改)
    6. [查看提交历史](#查看提交历史)
    7. [修改提交历史](#修改提交历史)
    8. [恢复到之前的提交](#恢复到之前的提交)
    9. [使用 .gitignore 忽略文件](#使用-gitignore-忽略文件)
2. [使用 GitHub](#使用-github)
    1. [将代码推送到 GitHub](#将代码推送到-github)
    2. [从 GitHub 拉取更改](#从-github-拉取更改)
    3. [创建新分支](#创建新分支)

## 在 VS Code 中使用 Git

1. **创建新文件夹**：首先创建一个目录，用于存放你的项目文件。
2. **在文件夹中创建文件**：将必要的文件添加到目录中，例如源代码或文档。

### 验证 Git 安装

在使用 Git 之前，确保它已正确安装，检查其版本：
```sh
git version
```
此命令将显示已安装的 Git 版本，如果系统中已安装 Git。

### 初始化 Git 仓库
要开始跟踪项目文件夹中的更改，需要创建一个本地 Git 仓库：
```sh
git init
```
此命令将在项目文件夹中初始化一个新的 `.git` 目录，Git 将使用它来存储所有版本历史和元数据。

### 查看文件状态
要查看文件相对于仓库的当前状态：
```sh
git status
```
**输出示例**：
```
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        how_to_use_vscode_with_github.md

nothing added to commit but untracked files present (use "git add" to track)
```
此输出表明 Git 检测到了一些新文件，但它们尚未被跟踪。未跟踪的文件是那些尚未添加到仓库版本控制中的文件。

### 追踪新文件
要将文件从“未跟踪”状态移到“已跟踪”状态，使用以下命令：
```sh
git add <filename>
```
例如：
```sh
git add guide.md
```
**输出示例**：
```
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   guide.md
```
文件 `guide.md` 现在已经暂存，这意味着它准备好被包含在下一个提交中。

### 提交更改
要保存已暂存的更改，需要创建一个提交：
```sh
git commit -m "关于更改的描述性消息"
```
`-m` 标志允许你包含一条描述更改的提交消息，以便更容易理解更改的历史。

### 查看提交历史
可以使用以下命令查看仓库中所有提交的历史：
1. 查看详细的提交历史：
```sh
git log
```
此命令显示每次提交的信息，包括提交 ID、作者、日期和提交消息。

**输出示例**：
```
commit 2f296dc9f7f1fa63b1acd406d3c61e182d0afcc3 (HEAD -> master)
Author: Yaemlt <jcd474747@163.com>
Date:   Sun Nov 17 22:47:27 2024 +0800
```
2. 查看简洁的提交历史：
```sh
git log --oneline
```
此命令以更简洁的形式显示提交历史，仅显示提交 ID 和消息。

**输出示例**：
```
2f296dc (HEAD -> master) Initial commit with VSCode setup
```

### 修改提交历史
要修改或删除特定的提交，可以使用 `git log --oneline` 命令查看提交 ID，然后执行后续操作，例如删除提交。

**输出示例**：
```
50adb32 (HEAD -> master) 删除了不必要的问号
d4edec9 更新了查看提交历史的说明
2f296dc Initial commit with VSCode setup
```

### 恢复到之前的提交
如果需要将文件恢复到某次提交时的状态，使用：
```sh
git checkout <commit_id> -- <filename>
```
要将整个仓库恢复到之前的状态并丢弃之后的所有更改，使用：
```sh
git reset --hard <commit_id>
```
此命令将把仓库恢复到指定的提交，并删除所有之后的提交。

### 使用 `.gitignore` 忽略文件
要指定 Git 不应跟踪哪些文件，可以在仓库根目录中创建 `.gitignore` 文件。添加要忽略的文件模式：
```
<filename>
```
例如，要忽略所有 `.log` 文件，添加：
```
*.log
```

## 使用 GitHub

### 将代码推送到 GitHub
如果想在 GitHub 上共享本地仓库，首先将其连接到远程 Git 仓库：
```sh
git remote add origin https://github.com/username/repository.git
git branch -M main
git push -u origin main
```
- `git remote add origin <url>`：添加一个新的远程仓库。
- `git branch -M main`：将当前分支重命名为 `main`。
- `git push -u origin main`：将本地仓库推送到 GitHub，并设置 `origin/main` 作为默认的上游分支。

### 从 GitHub 拉取更改
要将本地仓库与远程仓库中的更改同步：
```sh
git pull
```
此命令将从 GitHub 获取最新的更改并将它们合并到本地分支中。

### 创建新分支
要创建并切换到新分支：
```sh
git checkout -b <branchname>
```
这对于为新功能或实验性更改创建单独的工作区而不影响主代码库非常有用。

