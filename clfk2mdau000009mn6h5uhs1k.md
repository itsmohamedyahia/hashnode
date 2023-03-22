---
title: "Namespaces Abstracted"
datePublished: Wed Mar 22 2023 19:21:47 GMT+0000 (Coordinated Universal Time)
cuid: clfk2mdau000009mn6h5uhs1k
slug: namespaces-abstracted
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1679513823528/4300e797-d728-45ea-9d4d-3df3516531ef.png
tags: javascript, computer-science

---

## Prerequisites

* Objects in Javascript
    

Take a look at this piece of code

```javascript
const lion = {
  sound: function () {
    console.log("roar");
  },
};

const parrot = {
  sound: function () {
    console.log("hello!");
  },
};

lion.sound();   // roar
parrot.sound(); // hello!

// Here, we are creating two objects each having a function with the same name but different actions.
```

> The object is the **namespace** or the space in which the name of variables (inc. functions) exist and can be used.

If you want to create a function with the same name as another function, it has to be in a different namespace, and one way to create a namespace (a container or space) for certain names/variables is to create an object and define variables as keys in that object.

## Real Life Example

If your name is Mohamed, your family calls you Mohamed, no problem, right? But then you go to work and there are 2 other colleagues named Mohamed, in that case, usually what happens is that they call each of you by a different name than Mohamed, maybe call you by your last name or another name of your choice. So, having multiple Mohameds was no problem while they were in isolated environments (i.e their families) or as we should call it here "namespaces".

*I hope the concept of namespaces is now clear to you, if you have any other questions, feel free to ask them in the comments below. Thanks for reading and see you in the next one.*