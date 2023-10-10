---
title: "All About Arrays"
datePublished: Tue Oct 10 2023 23:19:25 GMT+0000 (Coordinated Universal Time)
cuid: clnky21g4000009mncs3paias
slug: all-about-arrays
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1696979905632/1671395d-105f-4859-863f-16d0d4e479a6.jpeg
tags: tutorial, javascript, web-development, webdev, beginners

---

> Not Really All

#### What are arrays?

Arrays are iterables.

#### Ok, so what is an iterable?

Iterables are objects that have `Symbol.iterator` method.

#### Alright, so what can we do with that method?

Well, they allow us to use `for` and `for..of` loops on those iterables.

#### If arrays are iterables, that must mean that iterables are a broader term that include things other than arrays.

You are right, iterables include `array-like objects`.

#### What are array-like objects?

They are objects which have a length property and we can access items added to that object with indices. That means that values are saved in indexed property names 0,1,2 and so on as in picture below.


![](https://upload.wikimedia.org/wikipedia/commons/f/fc/Array-like_object_has_a_symbol.iterator_method.png)

#### So what is the difference between arrays and array-like objects?

Well, lets list the similarities. Since both are iterables, this means both have `Symbol.iterator` method so both can be iterated upon using for..of and for loop.

But arrays, have many other methods which are not available on array-like objects like `filter`, `sort`, `map` and `forEach`.


![](https://upload.wikimedia.org/wikipedia/commons/4/45/Iterables.png)

#### If I want to use those array methods on array-like objects, I know they are not available on them but is there any way around that?

Fortunately, there is. You can convert array-like objects to arrays and then use those methods as you like.

```
const createdArrayFromArrayLike = Array.from('hi')
```

`Array` is an built-in object in js and we can use `from` method to create an array from such array-like object

#### How to create arrays

```
const array = [1,2]
const array2 = new Array(1,2)
```

#### I tried to create an array with one item using `new Array(5)` but got what appears to be an empty array ??!!

![](https://upload.wikimedia.org/wikipedia/commons/8/86/Empty_array.png)

Yes, because when you pass one item to it, it interprets it as the length of the array, so you will have an array with 5 empty indices and if you tried to console.log(array2[0]) or any index you will get `undefined`

> `const array = [1,2]` this is the best syntax to create array for simplicity and performance

#### How to deal with arrays, how to add items to an existing array, how to remove, tell me more about the methods I could use to manipulate arrays.

Certainly, lets first begin with adding items to an array.

`push`

```
const array = [1,2];
array.push(3)
console.log(array) // output: [1,2,3]
```

`unshift`

```
const array = [1,2];
array.unshift(3)
console.log(array) // output: [3,1,2]
```

let learn how to remove items

`pop`

```
const array = [1,2];
array.pop()
console.log(array) // output: [1]
```

Also if we want to save the `popped` or removed item pop method actually does that it returns the popped item, so

```
const array = [1,2];
const popped = array.pop()
console.log(array) // output: [1]
console.log(popped) // output: 2
```

`shift`

```
const array = [1,2];
array.shift()
console.log(array) // output: [2]
```
