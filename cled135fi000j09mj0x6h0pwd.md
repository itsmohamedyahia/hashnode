# Git add . vs Git add -a vs Git add -u

The difference between those three commands can be inferred from their parameters and flags.

```bash
Git add . 
```

**What does . mean?**

That's right. It means the current directory. So, `git add .` adds all files and folders located in the current directory including hidden files/folders.

```bash
Git add -a
```

`-a` flag is the shorter version of the `-all` flag, and as can be inferred it means adding all files and folders, but isn't that what `git add .` does? Well, you missed "the current directory" part. *I know you haven't missed it, smart guy, I am just playing with you* .

Getting back to the point, `git add -a` adds all files or folders in the whole repository, not just the current directory.

So that means if you modified a file in the repo main directory, `cd`'ed into a sub-directory, modified another file then ran the earlier command `git add .` you will only add the file in the subdirectory.

```bash
git add -u
```

`-u` flag is the shorter version for `--update` flag, and again as can be inferred, it means updating files and folders but there is a caveat, new files/ folders are not tracked,

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676909396026/bedf9104-8900-42d7-9a78-34595eaad661.png align="center")

and thus they can't be updated. So basically that means modified and deleted files/folders are added but not newly created ones.