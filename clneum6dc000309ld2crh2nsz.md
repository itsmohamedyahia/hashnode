---
title: "man pages"
datePublished: Fri Oct 06 2023 16:56:29 GMT+0000 (Coordinated Universal Time)
cuid: clneum6dc000309ld2crh2nsz
slug: man-pages
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1696611571670/5911459c-bcb9-4aa1-a761-230cdd329589.jpeg
tags: tutorial, terminal, cli, beginners

---

man pages or the manual pages is a documentation for commands installed on the system. Each command may or may not come with its manual page. The manual page describes the usage of the command and list all the options(operands) you can use on that command.  You can type an option followed by hyphen(s) after the command to change the behavior of that command.

Lets open the manual page for the command `ls`

`nuclearegg69@zenbook-f13:/var$ man ls`

`less` program will run and display the contents of the `ls` manual page

![Alt text](https://cdn.hashnode.com/res/hashnode/image/upload/v1696611140212/f306773c-61e1-49c5-8bc0-213e62a895fc.png)

first you will notice `(1)` afte ls at the first line. 1 indicates that this manual page is part of section 1 of the manual pages. Man pages is classified into 9 sections. You can learn more about them if you did `man man`



`nuclearegg69@zenbook-f13:/var$ man man`

As quoted from the manual page of man command


```
The table below shows the section numbers of the manual followed by the types of pages they contain.

       1   Executable programs or shell commands
       2   System calls (functions provided by the kernel)
       3   Library calls (functions within program libraries)
       4   Special files (usually found in /dev)
       5   File formats and conventions, e.g. /etc/passwd
       6   Games
       7   Miscellaneous (including macro packages and conventions), e.g. man(7), groff(7), man-pages(7)
       8   System administration commands (usually only for root)
       9   Kernel routines [Non standard]
```

So the first section is about executables including shell commands. `man`, `less`, `ls` are executables or shell commands.

### How to read the synopsis?


```
SYNOPSIS
SYNOPSIS
       ls [OPTION]... [FILE]...
```

`[]` brackets means that whatever is inside of them is optional. 
`OPTION` means any option -a, -h, -l so any option is optional
`FILE` means any object so a file or directory or other objects
`...` means or more so you can add 0 or more options to ls, 0 or more objects 

### How to navigate less

`q` to exit the less program of man
`up and down arrows` up and down a line
`b or ^B` back one view page
`f or ^F` forward one view page
`/` forward slash to search forward
`?` to search backward