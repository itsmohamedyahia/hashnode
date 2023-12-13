---
title: "Find logical operators + -size"
datePublished: Wed Dec 13 2023 23:27:14 GMT+0000 (Coordinated Universal Time)
cuid: clq4eimcb000008l30x8c5iie
slug: find-logical-operators-size
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1702509711246/bf0b4ca5-241a-4daf-9914-6caee7fcebb4.jpeg

---

### Logical operators in find

There are 3 logical operators we can use in find as options. They are `-not`, `-and`, `-or`.

Lets see how they are used. 

```
nuclearegg69@zenbook-f13:~/testRen$ ls
Apple  B  aa  banana  c  cactus  inNano2Ren  test2
nuclearegg69@zenbook-f13:~/testRen$ find -iname "a*"
./Apple
./aa
nuclearegg69@zenbook-f13:~/testRen$ find -iname "a*" -or -iname "b*"
./B
./Apple
./banana
./aa
nuclearegg69@zenbook-f13:~/testRen$ find -not -iname "a*"
.
./inNano2Ren
./B
./cactus
./test2
./c
./banana
```

In the first find command, we listed items that begin with an `a` with case sensitivity turned off
The second, we used `or` so `-iname "a*"` OR `-iname "b*"`
The third one, we listed files where the name doesnt start with a.

Note that we cant do:

```
find -iname -not "a*"
```
it might sound fine in english  "find files where the iname is not 'a'-starting", but the issue here is that `"a*"` is an argument, an argument to the -iname option. You cant seperate them by another option so -not  cannot not be between them and it also cant be after them because `-not` expects also an argument in the form of an expression (option +  its operand/argument)


### Finding by size

`find -size +50M` searches for files in the current directory that their size exceeds (denoted by + before 50M) 50 megabytes.
`find ~/Desktop -size -1k` searches for files in the `Desktop` directory in the home directory that their size is less than 1kb.

