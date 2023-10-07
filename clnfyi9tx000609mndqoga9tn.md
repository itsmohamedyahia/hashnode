---
title: "wc command"
datePublished: Sat Oct 07 2023 11:33:11 GMT+0000 (Coordinated Universal Time)
cuid: clnfyi9tx000609mndqoga9tn
slug: wc-command
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1696678320231/3b96a8c2-3e23-4140-8ec9-32d61749378c.jpeg
tags: tutorial, terminal, cli, beginners

---

The wc commands stands for word count

```
nuclearegg69@zenbook-f13:~$ ls
a  b  c  echo  empty  inNano3  inNano3.txt  inNanoRenamed  inNanoSymlink  testRen  testRen2
nuclearegg69@zenbook-f13:~$ nano a
nuclearegg69@zenbook-f13:~$ wc a
 5  5 58 a
```

When we pass a file as an argument to `wc` and run it, it gives us three numbers: the first is the line count, the second is the word count, the third is the bytes count. 

You can add options to wc to limit what you want

```
nuclearegg69@zenbook-f13:~$ wc -l a
5 a
nuclearegg69@zenbook-f13:~$ wc -w a
5 a
nuclearegg69@zenbook-f13:~$ wc -c a
58 a
nuclearegg69@zenbook-f13:~$ wc -m a
58 a

```

`-l` option gives you the lines only
`-w` words only
`-c` bytes only
`-m` characters only

