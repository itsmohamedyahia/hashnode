---
title: "All About Functions"
datePublished: Wed Oct 11 2023 22:31:38 GMT+0000 (Coordinated Universal Time)
cuid: clnmbsfuz000009ma85guf0wq
slug: all-about-functions
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1697063468194/c7714052-ea5d-4ca4-80b9-946da0e7f8ff.jpeg
tags: javascript, web-development, webdev, beginners, frontend-development

---

*Not All, I have tricked you.*

---

## typeof functions 

When you do `typeof <someFunction>`, you get back 'function'. But, you might have heard that functions are objects??

![image](https://upload.wikimedia.org/wikipedia/commons/0/0a/Typeof_functions_vs_console.dir_functions.png)

Well, they are indeed objects, if you do console.dir() on a function, you will get an object with key value pairs and a prototype, the reason why you get 'function' when you pass it as an operand to typeof operator is because that is the way typeof is configured

![image](https://upload.wikimedia.org/wikipedia/commons/4/42/Typeof_operator_results_from_ecma.png)

As you can see in the image, objects which are callable return 'function'

## function declarations vs function expressions

```
//function declaration

function doSth() {
  //do sth
}


// function expression

const doSth = ()=> {
  // do sth
}
```

#### what are the implications of using either one of those??

Functions and variables are hoisted (as if they are lifted up at the top of the code, metaphorically). But only the declaration is hoisted, this has a very important implications, variables will be declared but they will not be assigned a value (another term of assigning a value is initializating). That means if you call functions before they are declared, you can but if you try to access a variable before it is declared, you will get

![image](https://upload.wikimedia.org/wikipedia/commons/c/c3/Hoisting_variables.png)

> BONUS for English Non-native Speakers: hoisting actually means to lift sth up, it is not a word that is javascript-specific.
>
> The image below shows a hoist (lifter)
>

![image](https://alimak.com/nl/wp-content/uploads/sites/24/2020/11/Hero-image.jpg)

So, what are the implications again??

You can declare functions which are in the form of function declarations AFTER they are called but you can't with function expressions because they are variables and they are assigned a function (which is also a value or variable)

So you can do this

```
doSth()

function doSth() {
  //do sth
}
```

But not this

```
doSth()

const doSth = ()=> {
//do sth
}

```

#### What happens if I call a function that expects two arguments with one argument, will the function run??

Yes, it will run. The second argument will be undefined.

#### If I want to call a function but I dont know the number of arguments beforehand, what should I do?

There are two ways to do it:

**ES5 way**

```
function getSum() {
  let sum = 0;
  for (const number of arguments) {
    sum += number;
  }
  return sum;
}

console.log(getSum(1, 2, 3, 4));

```

**WHAT IS "ARGUMENTS", WHERE DID THAT ARRAY COME FROM??**

That is actually an array-like object, not an array. Array-like objects are objects that have a length property and have indices as properties which have array-like items as values

![image](https://upload.wikimedia.org/wikipedia/commons/f/fc/Array-like_object_has_a_symbol.iterator_method.png)

Array-like objects are `iterables` in js and that means we can iterate over them using `for..of` or `for i = 0` loops but not `forEach` because that is an array method.

`arguments` is a reserved keyword or variable and its value is an array-like object of all arguments you called the function with

**ES6 way**

With es6, we have a new operator called the rest operator.

```
function getSum(...numbers) {
  let sum = 0;
  for (const number of numbers) {
    sum += number;
  }
  return sum;
}
console.log(getSum(1, 2, 3, 4));

```

The rest operator simply combines values passed into an array. The naming behind comes from that we can do this:

```
function getSum(firstNumber, ...numbers) {
  let sum = 0;
  for (const number of numbers) {
    sum += number;
  }
  return sum;
}

```

Now the first argument passed will be assigned to firstNumber and **''the rest''** of the arguments will form an array called `numbers`

---
*That's the end of this article. Thanks for reading. I hope I have added something new to your arsenal of knowledge. If you liked the article, a quick thumps up or a comment would be appreciated and would help me continue sharing information. See you in the next one!*
