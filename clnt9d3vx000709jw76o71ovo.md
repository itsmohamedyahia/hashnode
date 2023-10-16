---
title: "npm projects"
datePublished: Mon Oct 16 2023 18:58:06 GMT+0000 (Coordinated Universal Time)
cuid: clnt9d3vx000709jw76o71ovo
slug: npm-projects
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1697482620769/46fca5c4-2591-4ca1-8d40-c2ec1833f4b2.jpeg
tags: web-development, nodejs, webdev, npm, frontend-development

---

To start an npm project, you can run `npm init` in the directory where you want to initiate the project. 

You will be prompted with some prompts about the name of the project and some other stuff that you can just skip by pressing `enter`. 

After that a `package.json` file will be created. It will in a `json` format as can be interpretted from the file extension.

JSON is a text-based format for representing JS Objects. JSON stands for Javascript Object Notation. 


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/hpg5q9gzmensxsv1y1ij.png)



That is the default content of the file. The two curly braces and what's inside them is a JSON object literal. 

#### Why literal or what does literal mean? 
Me too have wondered what is the meaning of literal that is shoved between text while the text itself makes sense without it `JSON object` is understandable without the literal in the end.  
Also, you might have heard about the literal syntax of declaring objects in javascript or the string literal. 

Literal is a notation (way of writing) for representing values. It is the "literal" notation of representing values. And literal here means the same meaning we know it for i.e. literally.
Lets make it more clear.

`let a = "boboddy"`

a is a string.
"boboddy" is also a string.

What is the difference between the two.

One is a variable representing the string, the other is the "literal" way of representing the string.

SO variables and constants cant be string literals or any value literal.

```
let stringVar = String("something")
```

so `String("something")` here is a value right? and it is a string because the string method will return a string as an output (it will get stored to stringVar but we are not talking about the variable here, we are talking about `String("something")` as a value. It is a string but it is not a `string literal` because it is not a literal string notation, the literal string notation is "something")

and the same goes for the other kind of values.

`5` is an integer literal but `2 + 3` is not. Neither is `Number("5")`. They are integers (in the sense that their `2 +3 ` expression will evaluate to `5` and the same goes for the other but they are not integer literals)

You would often hear about the literal syntax of declaring an object. It is like that:

```
let car = {
    model: "BMW",
    year: 2012
}

```
because those curly braces and the way of writing the key value pairs is the literal syntax.

```
let car = new Object();
car.model = "BMW"
car.year = 2012

```
That is another way of declaring an object but it is not the literal way.

I hope this is clear now.

---
Ok, lets go back. Where were we? Yes, JSON Objects. Ok, so you can see a JSON object with key value pairs. 
The `scripts` key contains a value of an object and this object consists of other key-value pairs. the default one we find is "test" but we can add more.
Every key we add to the `scripts` object is a script name and the value would the script itself (the script is a command or series of commands)

The first default script is `test` and when run it runs this line of code `echo \"Error: no test specified\" && exit 1`

So it will echo to the terminal "Error: no test specified" but not only that it will also run another command of `exit 1`

Scripts when run successfully exit with a code status of 0. 0 indicates success. In this case, yes, `echo` did run successfully but the script as a whole is a test script. we didnt run any tests, so it would be logical to assume that the script has failed (technically it didnt yes). In that case, we want to change the exit status to a number that indicates failure. Any number other than zero indicates failure. So they choose 1 as the exit status.
Note that line of code is just a placeholder for the actual test scripts we might have and we would like to replace this line with. 

Now, if your project is dependent upon a library like react or a framework, mostly you would find a `dev` key with some command. When you `npm run dev`, the app is running on a local server and you can make a request to the server through your browser in which the server responds with the  `index.html` file. 

Since we have learned earlier how an npm project is created and how can we manipulate the package.json file, and I told you when the `test` script runs it does blah blah blah but we didnt learn how to run it. 

Well, to run it, you open the terminal (VSCode Integrated Terminal) or any terminal program at the project directory and run `npm run ScriptNameInPackage.jsonFileWeWantToRun` so in our case `npm run test` 

```
PS D:\Teach\BLOGS\NPM> npm run test

> npm@1.0.0 test
> echo "Error: no test specified" && exit 1

"Error: no test specified" 
```
We could also do `npm test` and the script would run but that's for some special script names only like `test` and `start` (If we added a start script, it would run with `npm start` as well as `npm run start`). But for any other custom names we do, we have to run them using `npm run scriptName`

Now, why does a server spin up serving our web app when we do `npm run dev` in most web app projects using a library or framework?

Because the dev key is configured to a script that script will run a program/dependency (called dependency since our app depends on it to run) which will bundle the app and transform the code of the library or the framework into vanilla js along with html,css. This dependency might be vite or webpack or another program. 

My focus here is that `npm run dev` has nothing to do with those frameworks/libraries. You could create an empty directory, run `npm init` to initialize (hence init) an npm project, add an html file and add a `dev` key yourself whose value is `live-server`. live server is a program that spins up a local server which will serve your app. You have probably used it as an extension in vscode but you can also install it globally on your system by running `npm i -g live-server`. After you have installed it, you can run `npm run dev` in your directory and voila the html file is open in your browser. You can go back and add some text to the html file to confirm that it is indeed working. 


Just one more thing that is intuitive but the file is called package because its main purpose is to keep a list of all the packages (hence package.json) aka dependencies aka programs that your app needs to run. 


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/29ozemgvgb8qzff8hxic.png)


so in another key called `dependencies` it will store an object of the dependencies and the allowed versions so `^11.11.0` allows running newer minor verions so `11.12.0` is acceptable (middle or second number is the minor version, first is the major and the third i.e 0 in this case is for patch versions) 
*Read more about semantic versioning to get a clear idea of how versioning works* 

devDependencies is for dependencies that are used in the development environment for the development process but we dont need in production (also shorted prod).

---

And that concludes it. Hope you have enjoyed the read. If it wont bother you, leave a like or comment and share your thoughts.
