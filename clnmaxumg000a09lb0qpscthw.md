---
title: "Special Directories in Linux Root Directory"
datePublished: Wed Oct 11 2023 22:07:51 GMT+0000 (Coordinated Universal Time)
cuid: clnmaxumg000a09lb0qpscthw
slug: special-directories-in-linux-root-directory
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1697062014780/19395162-e837-4e6f-aa2e-ecf75417b927.jpeg
tags: linux, programming, beginners, linux-for-beginners, linux-basics

---

If we go to the root directory or the top level directory in our unix-like machine, we will be faced by some directories, lets take an intro about each one

```
nuclearegg69@zenbook-f13:~$ cd /
nuclearegg69@zenbook-f13:/$ ls
bin   etc   lib    libx32      mnt   root  snap  tmp
boot  home  lib32  lost+found  opt   run   srv   usr
dev   init  lib64  media       proc  sbin  sys   var
```

`bin` is a folder that contains binaries. Binaries are executable programs written in binary (hence binary). They are located under the top level dir directly because they contain common commands that all users use like ls, rm, and so on.

`etc` is a folder that contain configuration files. Configuration files for `nano` text editor and `chrontab` are there.

`root` is the home directory for the root special user. the root user has super priviliges over the normal user found under the `/home` directory. 

`home` is the parent directory for all users of the system

`media` or `mnt` is where external media devices like flash drives, dvds, external hard drives directories appear (depending on the linux distro)



