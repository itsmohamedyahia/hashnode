---
title: "window object and the DOM"
datePublished: Thu Dec 14 2023 10:48:43 GMT+0000 (Coordinated Universal Time)
cuid: clq52v0cp000p08ic7x6tcnav
slug: window-object-and-the-dom
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1702550894815/576485f9-1b61-4da7-899e-0e2e423780b1.jpeg
tags: javascript

---

When we query an element in js using `document.querySelector` syntax. We might would want to stop a bit and think about what we wrote `document.querySelector` looks like the syntax we use for properties on a object where the name before the dot (.) represents the name of the object and the name after the dot represent a property or method on that object. since `querySelector` is a function, we can say that querySelector is a method of the object document.

But where did that document object come from, we didnt create it. That object is created by the browser so that we could those functions that we also didnt create like querySelector.

You might hear a buzzword called the DOM. What does DOM stand for? DOM stands for document object model. The model of the document object. So now, what i understand that it has sth to do with that document object we were talking about earlier. Or they are kind of the same thing ..except for the 'model' part. Lets understand what the document object contains and we will come back the model part.

If we want to know what the document object contains, we might go to the console and write document and enter and we will get the html of the page


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/a7hpwcjb7fos207n7cb2.png)


SO now, I am confused is the document object the html code of the html document we wrote. But if that so, how is it an object, html is not javascript. Well that's because that's what the browser dev tools wants you to see. We know that an object contains key value pairs. 

To be able to see the real document object, we write `console.dir(document)`


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/uhx6ky0tqpobgjwgna9k.png)


If we scroll down, we will find a `children` property that has a value of type HTMLCollection.

HTML Collections are array-like objects. At its first index 0, we have some properties including an outerHTML, localName, nodeName all indicating that it is an object that represents the HTML element and if we scroll down we will find another children property which includes the head and body elements at index 0, 1 respectively.

This informs us that the document object is a representation of the html tree and the document object in itself the way it is designed through the children properties (@@looks like) a tree and that why it is called the document object model because it is modeling the html code.

When we use `querySelector` what it actually does is it searches the document object for the object that represents the element we are looking for and that object has properties attached to it and we can change those properties like 'element.backgroundColor' and set them to be something else just like we change properties on simple objects.

There is also another object that provided to us by the browser called the 'window' object. It also has some other properties like height and width of the current window/tab and other methods and actually one of its properties is the document object. SO the document object is a subset of the window object and that makes sense since the document object, which is a representation of the html code, is part of the window.
