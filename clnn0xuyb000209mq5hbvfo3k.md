---
title: "Expansion and Substitution in Unix-like Shells"
datePublished: Thu Oct 12 2023 10:15:41 GMT+0000 (Coordinated Universal Time)
cuid: clnn0xuyb000209mq5hbvfo3k
slug: expansion-and-substitution-in-unix-like-shells
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1697105677735/e8322b9f-b627-49c4-b29b-537412e0e08c.jpeg
tags: linux, terminal, bash, beginners, linux-for-beginners

---

## Pathname expansion

expanding a pathname, how do we do that?

if we do `echo 2 * 3`

```
nuclearegg69@zenbook-f13:~/testRen$ echo 2 * 3
2 a apple b banana c cactus inNano2Ren test2 3

```

I am presented with those what appears to be file names of current directory, all of them, the 2 and 3 are present at both ends but the asterisk * got replaced/expanded into those file names

This one of the wildcard characters that we can use for expansion. The following list contain some more: 

1. * asterisk: 
    - it matches 0 or more characters
    - ex: *.txt matches file.txt and 0.txt and .txt
2. ? question mark: 
    - matches any one character
    - ex: blue?.txt matches blue1.txt and bluez.txt but doenst match blue12.txt
3. [] square brackets or range wilcards:
    - they match a range of characters inside them
    - ex: [rbc]at matches rat, bat or cat
    - ex: [a-h]* matches any name that starts with a to h (case sensitivity matters so only small letters a to h) 
    - ex: [0-9]* matches any name that starts with a number

## Arithmetic expansion

```
nuclearegg69@zenbook-f13:~$ echo $((5+5))
10

```

syntax: `$((arithmetic_expression))`

## Command substitution 

```
nuclearegg69@zenbook-f13:~/testRen$ echo today is $(date)
today is Thu Oct 12 11:50:06 +03 2023
```

syntax: `$(command)`

## Changing-behavior Quotes

```
nuclearegg69@zenbook-f13:~/testRen$ a=5
nuclearegg69@zenbook-f13:~/testRen$ echo $a
5
nuclearegg69@zenbook-f13:~/testRen$ echo "$a"
5
nuclearegg69@zenbook-f13:~/testRen$ echo "\$a"
$a
nuclearegg69@zenbook-f13:~/testRen$ echo '$a'
$a
nuclearegg69@zenbook-f13:~/testRen$ echo "$((a+4))"
9
nuclearegg69@zenbook-f13:~/testRen$ echo '$((a+4))'
$((a+4))
nuclearegg69@zenbook-f13:~/testRen$ echo 1..9
1..9
nuclearegg69@zenbook-f13:~/testRen$ echo {1..9}
1 2 3 4 5 6 7 8 9
nuclearegg69@zenbook-f13:~/testRen$ echo "{1..9}"
{1..9}
nuclearegg69@zenbook-f13:~/testRen$ echo ~
/home/nuclearegg69
nuclearegg69@zenbook-f13:~/testRen$ echo "~"
~
nuclearegg69@zenbook-f13:~/testRen$ echo '~'
~
nuclearegg69@zenbook-f13:~/testRen$ echo *
a apple b banana c cactus inNano2Ren test2
nuclearegg69@zenbook-f13:~/testRen$ echo '*'
*
nuclearegg69@zenbook-f13:~/testRen$ echo "*"
*
nuclearegg69@zenbook-f13:~/testRen$ echo "`ls`"
a
apple
b
banana
c
cactus
inNano2Ren
test2
nuclearegg69@zenbook-f13:~/testRen$ echo '`ls`'
`ls`
```
Based on the above commands, we can deduce that:

1- double quotes: they disable all substitutions except those that involve a $ (dollar sign), \ (backslash), ` (backtick)

2- single quotes: disable all substitutions.



