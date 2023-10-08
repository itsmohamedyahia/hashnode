---
title: "Bash Redirection"
datePublished: Sun Oct 08 2023 12:02:07 GMT+0000 (Coordinated Universal Time)
cuid: clnhezbhz000e09jiea84esxe
slug: bash-redirection
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1696766500888/e24aaa25-3360-4b45-913d-c1b8141c43c4.jpeg
tags: terminal, bash, cli, beginners

---

When we run a process, a table named the file description table gets assigned to it. The table describes the relevant file contents to the process. If the process wants to read a file or write to a file (relevant file), that file gets assigned a numerical non-negative integer value and added to the table. This integer value is called a 'file descriptor'.

The 3 first values of the table are assigned by default so file descriptor 0,1,2.

File descriptor 0 is the `standard input (shorted for stdin)` of the process which is by default the keyboard input but could be changed to a file.  

File descriptor 1 is the `standard output` (shorted for stdout) of the process and it could be directed to a file. If the process is run from the terminal, the stout is by default the terminal so it gets printed in the terminal. 

File descriptor 2 is the `standard error` (shorted for stderr) of the process, also could be directed to a file and if ran from the terminal, the terminal is the default location of error output. 

## How to redirect?

### Redirecting standard input

```
cat < fileAsStandardInput.txt
```

This will pass the file as stdin to `cat`. Since the default stdout is the terminal. It will get printed in the terminal.

### Redirecting standard output

```
cat fileToBeRead.txt > outputFile.txt
```

`cat` will read the argument file and output the result to the `outputFile`. No text will be printed to the terminal

```
cat file2ToBeRead.txt > outputFile.txt
```
The file will be read and outputed to outputFile.txt. But if we read the file only the second file content is there. The first file content `fileToBeRead` is gone. That's because when the os opens the output file, it opens it in `write` mode.

If we want the text to be added to whatever is in that file, we have to open the file in the `append` mode. Fortunately, there's a way to do that.

```
cat file2ToBeRead.txt >> outputFile.txt
```

That way, the text will be appended


### Redirecting standard error

```
kfjalkfjlkkj 2> errorsLog.txt
```
`kfjalkfjlkkj` is not a command or maybe who knows if you were a maniac and made an alias for it. Anyways, naturally, an error would be printed to the terminal saying something across the lines of this is not a command. You can redirect that to the errorsLog.txt file using the command above. You could also append it using `2>>`. 

### Redirecting stdout and stderr to the same file

There is more than one syntax for that:

```
cat fileToBeRead.txt > outputAndError.txt 2> outputAndError.txt
```

```
cat fileToBeRead.txt 2>&1 outputAndError.txt
```

There is some newer syntax in newer versions of bash but let's not dive into that. You could search it though if you are interested.

Well, this concludes it. That was redirection. Thanks for reading and see you in the next article.