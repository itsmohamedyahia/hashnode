---
title: "File permissions in unix-like OSs ft. ls stdout"
datePublished: Fri Dec 22 2023 19:43:54 GMT+0000 (Coordinated Universal Time)
cuid: clqh1i2a6000008jmgylzg6bq
slug: file-permissions-in-unix-like-oss-ft-ls-stdout
tags: linux, bash, linux-for-beginners

---

```
nuclearegg69@zenbook-f13:~$ ls -l
total 56
-rw-r--r-- 1 nuclearegg69 nuclearegg69    0 Oct 10 07:55 1
-rw-r--r-- 1 nuclearegg69 nuclearegg69    0 Oct 10 07:55 2
-rw-r--r-- 1 nuclearegg69 nuclearegg69    0 Oct 10 07:55 3
-rw-r--r-- 1 nuclearegg69 nuclearegg69   84 Oct  8 15:33 a
-rw-r--r-- 1 nuclearegg69 nuclearegg69   27 Oct  7 15:08 alphabet.txt
```

When you run the list command with long option, you are faced with some data at the beginning of each file. `-rw-r--r-- 1 nuclearegg69 nuclearegg69 `.

**what does this mean?**

## Lets begin with `-rw-r--r--` (First Column)

- `-` means the object type, here it is a file, so it is denoted by `-`, directories are denoted by `d`, symbolic links are denoted by `l`

- `r` means the file can be read
- `w` means the file can be written upon so it can be modified
- `-` after `w` means file cant be executed

But `-` at the beginning meant that the object is a file.

Well, `-` is used as a negative symbol and if you counted the number of characters at that string of characters, you will find them to be 10 characters.

The first character is for the object type and i stated what character is used to represent each type. Then the rest are 9 characters which are divided into 3 groups of 3 characters.

- The first three characters represent the file permissions by the current user
- The second three characters represent the file permissions by the current user group
- The third three characters represent the file permissions for any user of the system

Let's break this out more:

- the first 3 characters out of the 9 characters `rw-`

  - if there is no read, write or execute permissions, it would be denoted by `---`. Now, we have `rw-` which means we have read and write permissions for the current user but no execute permissions.

- the second 3 characters are `r--`. This means the current user group has read permissions but write or execute permissions.

- the third 3 characters are `r--`. This means all other users have read only permissons.

and that's it for file permissions.

## Second column

> **Hey, Mohamed, before you leave. what about the 1 after the 10 file permission characters?**

> Excellent question, 1 denotes the number of hard links to that file in disk.

Hard links are essentially a pointer to that file. A pointer in the form of a file. So there can be two "apparent" "files" with different names in the same directory but when you edit one the other gets changed as if they are the same file. Well, indeed, they are the same file. When you do `ls`, you get back a list of directory entries and not "files".

Each directory entry is coupled with an inode number. The inode number identifies the inode. The inode is data structure or a table that contains metadata about that entry. That includes the name, size, number of hard links, modification time and more but more importantly it includes pointers that point to the data blocks in the disk storage that contains the entry data.

```
nuclearegg69@zenbook-f13:~$ ls -i
 6115 1    6092 a              4833 colt-ex   6062 inNano3.txt     2344 testRen2
 6115 1a   4823 alphabet.txt   6091 echo      1281 inNanoRenamed   6060 unsorted.txt
```

> \*Note that entry "1" and entry "1a" have the same inode number"

So, what we actually refer to as files are actually just file names or hard links with an inode number. And we can create hard links by doing `ln 1 1a` as i previously did.

## Third Column

The third column in line is `nuclearegg69`. This is the current username.

## Fourth Column

The fourth column being `nuclearegg69` is the current username group. And a group of users are just created to assign them similar permissions.

## Rest of Columns

- Fifth column is the file size in bytes
- Sixth column is the modification time
- And the last column is the file name.
