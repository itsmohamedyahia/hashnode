---
title: "Git Reset"
datePublished: Tue Dec 12 2023 00:02:21 GMT+0000 (Coordinated Universal Time)
cuid: clq1kw2b2000008jvewzrh7n9
slug: git-reset
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1702339298313/e0721129-2c6a-4bd2-8c0d-605ba8afc5d7.png
tags: programming-blogs, github, web-development, git

---



## Usecase

My most common usecase for git reset is when i stage changes by mistake. Maybe i make some changes that involve multiple things and i want to divide them into seperate commits. 

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/l815s5fz02qfnn8ybia6.png)

If you add them, git tells you this

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/g6wkdrwhq27ebxqi220b.png)


```
use "git restore --staged <file>..." to unstage
```

since you know `.` denotes the whole directory, you try `git restore --staged .` and it unstages the changes. Here comes `reset` with its shorter syntax, just `git reset` and voila your changes are gone. 

## Usage

`git reset` is mainly used to undo commits.
`git reset <commit hash>` and it will delete all commits up until that commit and most importantly KEEP THE CHANGES or to be most specific move the changes to the working directory.

That's why git reset without providing a commit, moves changes from the staging area to the working directory 

`git reset --hard` deletes the changes so if you run this command bare it will delete the working directory and the staging area GONE but UNTRACKED FILES ARE NOT AFFECTED. 

This behavior for untracked files is the same with any git reset command, it's not specific to the `hard` option.

`git reset --hard <commit hash>` will delete changes up to that commit.



