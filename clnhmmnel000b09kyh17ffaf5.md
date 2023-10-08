---
title: "Bash history"
datePublished: Sun Oct 08 2023 15:36:13 GMT+0000 (Coordinated Universal Time)
cuid: clnhmmnel000b09kyh17ffaf5
slug: bash-history
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1696779335023/1c4e1b57-4c99-4f46-b972-2ea894cae14e.jpeg
tags: linux, terminal, bash, cli, beginners

---

You can scroll the history of the commands you run by the up and down arrows in the terminal.

But in case you would like to look at the list of the comamnds you run you can type run `history`. It will print the commands in the terminal.

You can view them using less program by piping history to less `history | less`. 

Once you find the command you woould like to re-run just exit if you are in less type `!` followed by the line number of the command. 

What you have done now is called history expansion. It is called like that because `!1345` is expanded into the full command at the line number in the history file corresponding to the number you wrote.

The list file is located in the home directory under the name `.bash_history`