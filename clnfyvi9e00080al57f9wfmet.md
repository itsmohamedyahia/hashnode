---
title: "terminal vs shell vs cli vs bash— dont mix them up !"
datePublished: Sat Oct 07 2023 11:43:29 GMT+0000 (Coordinated Universal Time)
cuid: clnfyvi9e00080al57f9wfmet
slug: terminal-vs-shell-vs-cli-vs-bash-dont-mix-them-up
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1696766983091/b8838f14-0d78-416f-9168-50b80d2a546b.jpeg
tags: terminal, bash, cli, beginners

---

The terminal is a program that views text and allows you to write text

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ijv46qp5zk9uo0gv4z94.png)


That prompt for example `nuclearegg69@zenbook-f13:~$` is viewed by the terminal but the contents of that prompt are not dictated by the terminal but it is found and can be changed in the configuration files of the shell.

You could also change it temporarily in that terminal session by setting `PS1=promptYouLike`, just type in the terminal, enter and voila (You could also change it permenantly by changing it in the config file).

The shell is part of the OS and is the interface to the kernel. The kernel is the part of the OS which deals with hardware, starts processes, allocates memory and cpu resources.

You can also run the terminal without the shell. When you open less, that's not the shell. That's an executable program which runs in the terminal but is not part of the shell. If it by default 'there' for you to use that doesnt mean it is part of the shell. It is just preinstalled. You can verify whether the command you are running is part of the shell or not by running `type command`. If it gives a location in /usr/bin, it is not part of the shell. 

When you run python repl or the node js repl on the terminal, you are not running the shell but the terminal is running.

When you exit the python or nodejs repl thats when you return running the shell.

And you could also use the shell without the terminal. 

The desktop GUI also interacts with the shell. When you double click on an item to open in the default associated program by the OS, you have now interacted with the shell and the shell will send to the kernel to start a process of the program you have just clicked if it is an executable or the associated program with that file.

You could also write script files in bash scripting language for example and then run the script by double clicking it from the gui. Now you have interacted with the shell two times, when you ran the script and the when the script was run.

The terminal correct term would be a terminal emulator because back in the days computers were large. They would take up a room and. The computer cpu time was shared among multiple users through terminals which were devices that had a screen and a keyboard. You would write the processes that you would like to run on the cpu, the cpu would 'process' them, return the output which would be displayed on the screen. Much like software terminal nowadays.

Bash is a shell. There are other shells out there like zsh, sh, powershell and more. Bash was inspired from sh which is unix os shell. Actually bash stands for Bourne Again SHell. Bourne is the name of the creator but also is close to the word 'born'. The H in SHell is not a capital letter by mistake. It is in the capital form to highlight the two letters SH which is sh shell. So the full name implies that bash is the sh shell born again while also indicating the creator and that it is a shell. Very creative naming indeed. 

What about the command-line interface? Where is it in that picture? command line is the line where you type your commands so the terminal might be referred as the command line interface because it is an interface where you type your lines of commands. The shell itself also can be interpretted as a command line interface because the command lines are sent to the shell where it evaluates them and sends calls to the kernel to perform those operations. 