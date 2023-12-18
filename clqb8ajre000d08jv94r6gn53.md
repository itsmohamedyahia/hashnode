---
title: "Closures !!"
datePublished: Mon Dec 18 2023 18:07:23 GMT+0000 (Coordinated Universal Time)
cuid: clqb8ajre000d08jv94r6gn53
slug: closures
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1702922766517/b7312b36-8da3-49f7-b63d-daa37e0996f4.png
tags: javascript, web-development, webdev

---

A closure is a function with its outer lexical scope/environment.

What does 'lexical' mean?

- 'Lexical' means relating to words, so the 'lexical scope of a function' is the scope related to the wording of that function or the definition of that function.

```js
function doSth() {
  //some code
  function doSthFancy() {
    // do sth fancy
  }
}

function doSthElse() {
  doSth();
}

doSthElse();
```

The 'lexical scope' of the function above `doSth` is the global context since it is worded/defined in the global space, but the invocation scope is the doSthElse function space since it runs there.

Now back to the closure definition.

> A closure is a function lexical scope with its outer function lexical scope/environment.

So, what is the closure of doSth? its `doSth` + `global scope` (which contains doSthElse as a variable).

Why we were able to run doSth from doSthElse? Because doSth is in the lexical scope of doSthElse (lexical scope of doSthElse is the global scope and doSth is defined there so it is available for doSthElse to use).

BUT if we added `doSthFancy`,

```js
function doSthElse() {
  doSth();
  doSthFancy();
}
```

and tried to execute doSthElse, it would throw an error complaining that doSthFancy is not defined.

So, why is a closure useful? JUST A DEFINITION!?

Let's see.

First: (which is the boring usecase)

```js
function outerFunction() {
  let variable = "some variable";

  function innerFunction() {
    console.log(variable);
  }
  innerFunction();
}

outerFunction(); // 'some variable'
```

If we ran outerFunction, 'some variable' is console logged but why? There is no `variable` variable declared in the `innerFunction`, how did `innerFunction` get the value of variable from the `outerFunction`? That is because functions have access to variables declared within its lexical scope which includes the `outerFunction`.

SO BORING YES, but watch this:

```js
function outerFunction() {
  let variable = "some variable";

  function innerFunction() {
    console.log(variable);
  }

  return innerFunction;
}

const someFunction = outerFunction();

someFunction();
```

NOW, in the assignment of `someFunction` to the `outerFunction` call, the `innerFunction` is returned AND it didnt run. Outer function got executed, finished executing, no longer there in the call stack, variable value is not there anymore sinced its gone.

BUT then we run the innerFunction at `someFunction()` where the invokation context now is the global space and there is no `variable` variable there so the console log value should be undefined BUT THAT IS NOT THE CASE.

The logged value is 'some variable' MAGIC? No, its closures baby. That function `someFunction` gets the variables defined in its lexical scope when it is invoked to work with.

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/i1qba36nc9xvci69tjyi.png)

You might be thinking now, that's interesting. You know what is more interesting? `You`. Nah, I am joking. You are not that interesting or you are but you know what's more interesting? You're not falling for it again, huh. Ok, what's more interesting is that `someFunction` doesnt only get its lexical scope but also its parent/outer function lexical scope, watch this.

```js
function outerOuter() {
  function something() {
    console.log("something");
  }

  function outer() {
    return function inner() {
      something();
    };
  }

  return outer;
}

const outer = outerOuter();
const inner = outer();

inner(); //something
```

The lexical scope of the parent function is this

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/fdeafo2k6m3fovzfx616.png)

and that's why 'something' was logged

## Practical Example for closures

Lets say we have some buttons and we want to run event handlers when they are clicked

```js
button.addEventListener("click", () => {
  document.body.appendChild("div");
});
button2.addEventListener("click", () => {
  document.body.appendChild("p");
});
button3.addEventListener("click", () => {
  document.body.appendChild("a");
});
```

`document.body.appendChild` is repeated in these 3 handlers, I dont like that, the only thing changing is the element name. so what can we do?

Well the first guess is that we would make a function that accepts that dynamic/changing part as a parameter and it would return that repeated logic with the element name that it got passed

```js
function appendEl(el) {
  document.body.appendChild(el);
}
```

Spectactular. Now we only have to pass that function as the event handler of the click event

```js
button.addEventListener("click", appendEl(el));
```

Is that right? Nope, because we are not passing a function, we are invoking it and what we are actually passing is the evaluation of the appendEl call which is the return value of it which is undefined. so how could we solve this?

an easy way would be this

```js
button.addEventListener("click", () => {
  appendEl("div");
});
```

To just add it as the function body of another function

Another solution would be to use bind (and it is more useful in some cases where we need to assign the `button` object to `this`)

```js
button.addEventListener("click", appendEl("div").bind());
```

Third solution which I consider the cleanist is by making appendEl return a function containing the logic.

\*\* ALERT: HIGHER ORDER FUNCTION INCOMING \*\*

```js
function appendEl(el) {
  return function () {
    document.body.appendChild(el);
  };
}

button.addEventListener("click", appendEl("div"));
```

Then we could just do this. Now `appendEl` will return a function and when it runs it will need the el variable which will be present for the inner function to use even though `appendEl` ran and finished execution and that was made possible by CLOSURES.

---

That is the CLOSURE of this article (see what I did there!), hope you enjoyed it, understood it, and sEe yOu iN tHe nExT oNe.
