---
title: "Exploring Nodejs Series: Chapter 1"
datePublished: Tue Jun 13 2023 19:55:11 GMT+0000 (Coordinated Universal Time)
cuid: cliupd0ov000008lcb1lp170d
slug: exploring-nodejs-series-chapter-1
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1686680891872/d1ac7ef3-129f-48e3-b7f1-619fa9bacac0.png
tags: web-development, nodejs, backend, webdev

---

* Nodejs runs JS Code. **HOW?**
    
    * using the v8 engine by Google. **WHAT DOES IT DO?**
        
        * compiles js code to machine code. **WHY NOT CALL IT A COMPILER THEN?**
            
            * because it does more than compiling, there is garbage collection, optimization techniques, and it doesn't do classic compilation but Just-in-time compilation ( compiles and executes as it parses)
                
* Nodejs is a JS Runtime. **Runtime??**
    
    * it is an environment in which js code runs and provides everything needed for it to run.
        
    * examples of runtimes: browser, node js
        
    * environment includes:
        

1. JS engine
    
2. API methods (ex. document.querySelector(), a method not available in bare js, the browser provides document object which contains many methods to interact with the DOM)
    
3. In nodejs, there is a global object which contains many methods too
    
    * ex: `const myModule = require('./myModule');`
        
    * require method is part of `global` object but we dont need to write `global.require` as nodejs recognizes by itself, if it doesnt see a custom require function declaration set by us, it will default to global require method
        
4. In nodejs, there is JS additional features or extensions (Nodejs Modules), one of which is `fs` module which allows to interact with the file system.
    

> BONUS TIME:
> 
> Firefox uses spidermonkey engine.
> 
> V8 is written is C++.

* **Runtime?? why it is called a runtime when it is an environement?**
    
    * well, a runtime from the name should indicate time (period) of running and that is correct, it refers to the period in which a program runs. so if a program happens to run infinitely, we would say its runtime is infinite, but it also refers to the environment in which that program runs. think of an environment as a box which contains a juice cans factory (js engine) and other things like water supply to the factory (browser api methods, nodejs modules) which supplement that engine to run the code it's given.
        
* **Require Method?**
    
    * used to import nodejs modules.
        
    * we would write `const myModule = require('./myModule');` at the top of the JS file (convention, just to make you and others know what modules are required for this file to run, but you can write it anywhere as long as you use methods of that module or object after importing (or declaring that statement above). **why did you say a module is an object??**
        
        * a module is just a js file that contains some js code or functions and if you want to make those functions available to be used in other js files, you have to export them *(read about es6 modules if you are not familiar)*, so what we do instead of exporting every function in that file, we will export an object which contains all the functions in that file. so, when we do `const myModule = require('./myModule');` we are importing an object `require('./myModule')` and we are assigning myModule a reference *(read about reference variables if you are not familiar)*
            
    * back to the topic, let's give a real example:
        
        ```javascript
        cosnt fs = require('fs')
        fs.writeFileSync('filename.txt', 'this is the content i want to write to that file')
        ```
        
        We said that fs is a reference to the object or lets for simplicity say fs is the object we exported, now we can use dot notation to access methods stored in that object, one of which is writeFileSync, which from the name suggests that it writes files synchronously so it will create a file with the name we specified in the first parameter and content in the second parameter. if the file is already created, it will replace its content with the content we specified. **WHY DID YOU WRITE** `require('fs')` **and not** `require('./fs')` **??**
        
        * because we use `require('./fs')` if we are referring to a module that is present in the current directory or folder, the parameter we give to require in that case is the file path, we could give it an absolute path or a relative one (INFRA it yourself). that is a relative one and the `.` means the current directory but `fs` module is a core module, which means it is available to us (to import) without downloading it or importing it from the cloud or sth , and so, we just write the module name `require('fs').`
            
        * `fs` stands for file system, it is a module which contains many methods to deal with the file system (read files, write files, append \[add content to a file without replacing content\])
            
* **I want to try running js code using nodejs without executing a file, something like chrome dev tools console in the browser, HOW TO DO THAT?**
    
    * you could enter REPL mode by opening your os terminal and writing `node`, then you can run js code
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686681596490/b2b5fb85-fbf5-431f-8f03-5755816042b4.png align="center")
        
        **what does REPL mean??**
        
        * repl stands for (read, evaluate, print, loop) so it reads your statement (code), evaluate it (execute) and print either side effects of your statement in case of console.log() which is `hello world` for example and prints return value of your statement `undefined` since the return value of console.log() function is undefined and loop, it gives control back to the user to write another statement as viewed by `>` symbol.
            

---

This chapter concludes here, and I hope you enjoyed it. If you have any questions, please feel free to ask them below. Additionally, I welcome any corrections or valuable information you may have to contribute.

*The content of this series draws inspiration from* [*Maximilian Schwarzmüller's Node.js course on Udemy*](https://www.udemy.com/course/nodejs-the-complete-guide/)*, serving as an index for the topics covered. However, it should be noted that the content reflects my personal interpretation and additional research conducted by me.*