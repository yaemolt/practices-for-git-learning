# git learning path

## using git in VS Code

1. create your folder
2. create your file in your folder

### check whether your git is ready
```
git version
```

### create .git file
```
git init
```

### check file status
```
git status
```

output:

```
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        how to use vscode with github.md

nothing added to commit but untracked files present (use "git add" to track)
```

### untrack-->tracked
```
git add <filename.type>
```

output:

```
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   guide.md
```

### commit changes
```
git commit -m "name for changes"
```

### view changes history

1.
```
git log 
```

output:

```
commit 2f296dc9f7f1fa63b1acd406d3c61e182d0afcc3 (HEAD -> master)
Author: Yaemlt <jcd474747@163.com>
Date:   Sun Nov 17 22:47:27 2024 +0800
```

2.
```
git log --oneline
```

output:

```
2f296dc (HEAD -> master) 写到提交修改了
```

1. -->delete a '?'
2. -->commit

```
git log --oneline
```

output:

```
50adb32 (HEAD -> master) delete ?
d4edec9 写到查看提交历史了
2f296dc 写到提交修改了
```
