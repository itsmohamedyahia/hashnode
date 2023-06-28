---
title: "GIT Stash"
datePublished: Wed Jun 28 2023 15:31:26 GMT+0000 (Coordinated Universal Time)
cuid: cljfvjmj7000009mhcb4p321q
slug: git-stash
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1687966222602/8d143f93-1c26-4a27-a57c-07c2eab39aec.png
tags: tutorial, git, beginners

---

## Usecase

Suppose you are working on a git branch, you have some changes, maybe you have some changes that in the working directory while some other changes you have staged them, but for whatever reason you want to check the main branch or any other branch for sth and you dont want to commit any changes yet.

If you try to check to another branch while not commiting changes, there are two scenarios that could happen

A- You could checkout without issues but if you do `git status`, you will find that changes you have made in branch A (branch `master` in the image) came with you

![image](https://drive.google.com/uc?id=1RSS8aI27RovO1xjD66E16Eqqu-3lXOPo align="left")

B- You cant checkout because your changes conflict with code or file content on branch B (branch 'new' in the image)

*I committed some changes to branch* `new` and then branched from it to `radical` , I didnt do anything on radical and went back to `new` did some changes on a line and committed, then switched to `radical` and there did some changes on the same line I just changed on `new` and then we I tried to came back to `new` without committing, I got this

![image](https://drive.google.com/uc?id=1scoZEToGs-UGNYt4gM8e3VMn1CQUnB6g align="left")

I cant switch unless I stash, commit, or reset (git reset deletes changes).

So, there lies the issue and there lies the solution. `git stash`.

## Usage

`stash` (for non-native english speakers) means to and I quote:

```javascript
 When you stash something, you stow it away to use it later. Your
little brother might stash his Halloween candy under his bed, for
 example.
```

```javascript
 Use the word stash as a verb that means "hoard" or "stockpile," or as
 a noun — a pirate's secret pile of gold doubloons can be called a
 stash, and so can the collection of overdue library books you've got
 piled beside your bed. The verb version of stash was originally a late
 1700's criminals' slang word meaning "conceal." It may have come from
 a combination of stow and cache.
```

"Stash." Vocabulary.com Dictionary, Vocabulary.com, https://www.vocabulary.com/dictionary/stash.

Now that the meaning is very clear, the action of `git stash` does exactly what it means, it stores the changes (of the working directory and the staging area/index) (in a storage box, just imagine) and you can get them out later using `git stash pop`

![image](https://drive.google.com/uc?id=12sB9cXFwKb8Ykmm6vLZDMp7FTbukbIyW align="left")

> You can 'pop' them or get them out of the stash at any branch so it doesnt have to be from the same branch you stashed them from

## QoL

There are some 'quality of life' commands that you might be interested in.

`git stash apply`: similar to `git stash pop`, but instead of getting the changes out of the stash and applying them (the stash will be empty after git stash pop), `git stash apply` just 'paints' the changes to the current branch or to be more clear applies them but leaves the changes in the stash (or the stash) as is, so you can apply the stash to multiple branches

`git stash list` lists all stashes you have, yes, you can have multiple stashes

```javascript
Mohamed Yahia@DESKTOP-J80K0ID MINGW64 /u/test (main)

$ git stash list
stash@{0}: WIP on master: 5f33582 done
stash@{1}: WIP on master: 5f33582 done
```

> stash 0 will always be the latest stash. so first stash you make is 0 then if you do another stash, the first stash will be 'stash 1' and the second or latest one will be 0.

`git stash show -p 0` or `git stash show -p stash@{0}` if you would like to see what changes will be done before applying the stash, you could run this command

`-p` stands for patch so it views the changes in a patch format, why is it called a patch format?? well, if you used any app, program or game, when they do a patch update, they release 'patch notes' and what are they? yes, they are a list of the changes, so here, it is the same, 'patch' lists the changes

If you dont pass the stash number or name, you will get a diff of the latest stash so stash 0.

```javascript
Mohamed Yahia@DESKTOP-J80K0ID MINGW64 /u/test (master)

$ git stash show -p stash@{0}
diff --git a/sth.txt b/sth.txt
index 40cf306..0cec393 100644
--- a/sth.txt
+++ b/sth.txt
@@ -1,2 +1,4 @@
 luck
 duck
+
+tuck
```

`git stash drop 1` will delete stash number 1 (if no number then latest stash) `git stash clear` delete all stashes

---

*And that's it for git stash. Feel free to leave feedback below and thanks for reading.*