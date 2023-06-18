---
title: "Defer vs Async vs Default Browser Behavior"
datePublished: Sun Jun 18 2023 13:24:12 GMT+0000 (Coordinated Universal Time)
cuid: clj1glhjq000609l09ki32aex
slug: defer-vs-async-vs-default-browser-behavior
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1687094499870/9bb397b9-6f02-4710-89d1-ae04b944a8c3.png
tags: tutorial, javascript, web-development, beginners, frontend-development

---

## Default Behavior

![default](https://upload.wikimedia.org/wikipedia/commons/8/8f/Default_behavior_of_browser_when_parsing_html.png align="left")

1. html is getting parsed
    

EVENT: it gets across script element

1. html parsing stops
    
2. js file is getting downloaded
    
3. js file is parsed and executed
    
4. html continues getting parsed
    

## DEFER

![defer](https://upload.wikimedia.org/wikipedia/commons/8/8b/Browser_behavior_when_defer_attribute_is_added_to_script_element.png align="left")

1. html is getting parsed
    

EVENT: it gets across script element

1. html continues parsing AND SIMALTANEOUSLY js files gets downloaded
    

EVENT: html parsing finished

1. js file gets parsed and executed
    

DEFER means 'postpone' or 'do sth at a later time' so the parsing of js and execution is 'deferred' BUT loading is not

Not always is js file execution is waiting for html to be finished getting parsed, sometimes, js file execution is waiting for js file to load because it takes longer than html parsing.

![incident](https://upload.wikimedia.org/wikipedia/commons/f/f6/Incidence_of_browser_reading_html.png align="left")

## ASYNC

![async](https://upload.wikimedia.org/wikipedia/commons/a/a9/Browser_behavior_when_async_attribute_is_added_to_script_element.png align="left")

1. html is getting parsed
    

EVENT: it gets across script element

1. html continues parsing AND SIMALTANEOUSLY js files gets downloaded and executed
    

HTML is parsed and JS is processed (loaded and executed) regardless of any events happening, totally asynchronously.

---

I hope this was clear. If you have any questions, please feel free to ask them below. Additionally, I welcome any corrections or valuable information you may have to contribute.