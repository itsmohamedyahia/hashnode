---
title: "Shell commands - pwd & ls"
datePublished: Fri Oct 06 2023 17:08:15 GMT+0000 (Coordinated Universal Time)
cuid: clnev1bf4000f08if4k0o0sby
slug: shell-commands-pwd-ls
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1696612050165/09a84b39-c404-4e90-afe3-d0d7f4fbd71f.jpeg
tags: tutorial, terminal, cli, shell, beginners

---

### pwd command

- it lets you print out the path of the current working directory
- pwd stands for print working directory
```
nuclearegg69@zenbook-f13:~$ pwd
/home/nuclearegg69
```

### ls command

- it lists files and directories(folders) inside current working directory except for hidden files

- ls stands for list

```
nuclearegg69@zenbook-f13:~$ ls
a  b  c  d  e  test
nuclearegg69@zenbook-f13:~$ ls test
a  apple  b  banana  c  cactus  test2
```
- you could also provide an argument for the ls command to list the contents of the argument folder

#### ls options

- `-a` lists ALL files and directories and that means including hidden files. hidden files start with a dot `.` 

```
nuclearegg69@zenbook-f13:~$ ls -a
.   .bash_history  .bashrc  .hushlogin  .local       .profile         .sudo_as_admin_successful  a  c  e
..  .bash_logout   .cache   .lesshst    .motd_shown  .python_history  .zcompdump                 b  d  test
```


- `h` lists contents in human-readable format
```
nuclearegg69@zenbook-f13:~$ ls -lh
total 4.0K
-rw-r--r-- 1 nuclearegg69 nuclearegg69    0 Oct  3 19:07 a
-rw-r--r-- 1 nuclearegg69 nuclearegg69    0 Oct  3 19:07 b
-rw-r--r-- 1 nuclearegg69 nuclearegg69    0 Oct  3 19:07 c
-rw-r--r-- 1 nuclearegg69 nuclearegg69    0 Oct  3 19:07 d
-rw-r--r-- 1 nuclearegg69 nuclearegg69    0 Oct  3 19:07 e
drwxr-xr-x 3 nuclearegg69 nuclearegg69 4.0K Oct  5 02:33 test
```
- `l` lists contents in long format 

```
nuclearegg69@zenbook-f13:~$ ls -l
total 4
-rw-r--r-- 1 nuclearegg69 nuclearegg69    0 Oct  3 19:07 a
-rw-r--r-- 1 nuclearegg69 nuclearegg69    0 Oct  3 19:07 b
-rw-r--r-- 1 nuclearegg69 nuclearegg69    0 Oct  3 19:07 c
-rw-r--r-- 1 nuclearegg69 nuclearegg69    0 Oct  3 19:07 d
-rw-r--r-- 1 nuclearegg69 nuclearegg69    0 Oct  3 19:07 e
drwxr-xr-x 3 nuclearegg69 nuclearegg69 4096 Oct  5 02:33 test
```
- `--sort=someSortingCriteria` intuitive
```
nuclearegg69@zenbook-f13:~$ ls -l --sort=time
total 4
drwxr-xr-x 3 nuclearegg69 nuclearegg69 4096 Oct  5 02:33 test
-rw-r--r-- 1 nuclearegg69 nuclearegg69    0 Oct  3 19:07 d
-rw-r--r-- 1 nuclearegg69 nuclearegg69    0 Oct  3 19:07 e
-rw-r--r-- 1 nuclearegg69 nuclearegg69    0 Oct  3 19:07 a
-rw-r--r-- 1 nuclearegg69 nuclearegg69    0 Oct  3 19:07 b
-rw-r--r-- 1 nuclearegg69 nuclearegg69    0 Oct  3 19:07 c
```
