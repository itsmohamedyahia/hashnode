---
title: "sort command"
datePublished: Sat Oct 07 2023 12:23:01 GMT+0000 (Coordinated Universal Time)
cuid: clng0acr6000109mfesrl306o
slug: sort-command
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1696681356196/a6bdbafb-2b05-4f47-9299-d2ab126403c5.jpeg
tags: tutorial, terminal, cli, beginners

---

### The default function of sort command and the -r or --reverse option

```
nuclearegg69@zenbook-f13:~$ cat unsorted.txt
white apple
yellow orange
black banana
hannah montana
cheetah in the savanna
nuclearegg69@zenbook-f13:~$ sort unsorted.txt
black banana
cheetah in the savanna
hannah montana
white apple
yellow orange
nuclearegg69@zenbook-f13:~$ sort -r unsorted.txt
yellow orange
white apple
hannah montana
cheetah in the savanna
black banana
```

### -u option or --unique prints only unique lines while sorting


```
nuclearegg69@zenbook-f13:~$ nano unsorted.txt
nuclearegg69@zenbook-f13:~$ cat unsorted.txt
white apple
white apple
yellow orange
yellow orange
black banana
hannah montana
cheetah in the savanna
nuclearegg69@zenbook-f13:~$ sort -u unsorted.txt
black banana
cheetah in the savanna
hannah montana
white apple
yellow orange
```

### Sorting numbers 

```
nuclearegg69@zenbook-f13:~$ cat unsortedNums.txt
1
2
188
9
78
nuclearegg69@zenbook-f13:~$ sort unsortedNums.txt
1
188
2
78
9
nuclearegg69@zenbook-f13:~$ sort -n unsortedNums.txt
1
2
9
78
188
```

The sort command by default doesnt work for numbers because it compares character by character so first number in 188 is 'more up in the list of numbers' than 2 so 188 goes first, so we have to use -n or --numeric-sort for it work as we would expect.