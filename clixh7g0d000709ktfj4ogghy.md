---
title: "Exploring Nodejs: Chapter 2 — URLS AND THE INTERNET"
datePublished: Thu Jun 15 2023 18:30:12 GMT+0000 (Coordinated Universal Time)
cuid: clixh7g0d000709ktfj4ogghy
slug: exploring-nodejs-chapter-2-urls-and-the-internet
tags: tutorial, web-development, nodejs, backend, webdev

---

Chapter 2 is here! In this chapter, we will talk about how the internet works, what happens when we go to a url, different parts of the url and how does DNS Servers help us traverse the web. Hope you enjoy it.

---

### WHAT HAPPENS UNDER THE HOOD WHEN I ENTER A URL IN THE BROWSER ADDRESS BAR??

Well, you need to know what a URL is. **OKAY, WHAT IS A URL??**

URL stands for 'uniform resource locator'. **WHY??**

'Uniform' since all URLs have a uniform and standard structure

'Resource Locator' since that URL is used to locate a file or a 'resource' on the internet or even locally on your computer.

and it consists of some parts as shown in the image:

![url constituents](https://upload.wikimedia.org/wikipedia/commons/thumb/b/ba/URL_structure.jpg/800px-URL_structure.jpg?20200419144644 align="left")

>A picture showing URL structure. Illustration made by [Noémie2602](https://commons.wikimedia.org/w/index.php?title=User:No%C3%A9mie2602&action=edit&redlink=1) and licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.en).

Lets focus on the domain for a second, we refer to `wikipedia` as the domain or [`en.wikipedia.org`](http://en.wikipedia.org) can be called the domain name too,

## HEY, WHY IS IT CALLED A DOMAIN??

Just wait for a second, be patient, that domain, mmm, well, lets get back a second, i get back a page when i enter the url, **BUT WHERE IS THIS PAGE STORED??**

This page is stored on a computer like the one you are reading from right now, but if that computer's sole purpose is to serve files then we would call it a server, makes sense, so i enter the domain part (which is the unique part of a url if we are writing [`https://www.google.com/`](https://www.google.com/)) and then my browser magically knows that it should get a file from another computer across the internet, **IS THAT IT?**

Well, it's not magic once you understand what happens, we have to think first how did our browser could get to that other computer, they have to be connected, right?? and they are both connected to the "internet".

### **WHAT IS THE INTERNET EXACTLY, IS THAT SOME CLOUD IN THE SKY?**

The internet is very simpler than what most people have in mind, it is just wires, yes, your computer is connected to that other computer(server) through a wire unless you are connecting to a wifi then most of the pathway is wires. In the case of you connecting to a wifi, that wifi will be connected to your router then a modem (or a 3-in-1 device) then to your ISP infrasture (which is basically routers) and your ISP is connected to other main ISPs and so on and there are wires that cross seas and oceans to connect the whole world together! (If you are interested, you can see actual footage of the physical infrastructure of the 'internet' through [this youtube video](https://www.youtube.com/watch?v=TNQsmPf24go&ab_channel=Vox))

When a computer is connected to a router, it is given an ip address and your router also has an ip address, every device basically that is connected to the internet has an ip address to identify it from the rest of devices, just like a home address so that data which is travelling across the 'web' or 'internet' or wires knows where to go to. Now, to get a file from another computer, you have to request it, just like humans in real life, if you want something, you request it, the server then returns a response which might include the website files.

When you enter an ip address in the address bar, the browser sends a request to the server to fetch the files, the file or files sent back is determined by a set of code which tells the server, hey, if you get a certain request, send a certain response. That set of code is the 'backend' and can be written by multiple languages, one of which is Javascript and will be run by Nodejs, the runtime environment.

## **BUT WE ARE NOT WRITING IP ADDRESSES, ARE WE??**

Well, we could, but for convenience, we are writing a url which the unique part of is the domain name. **DOES A SERVER HAS A DOMAIN NAME SO THAT WE COULD IDENTIFY IT WITH??**

No, servers have ip addresses. **BUT HOW DO WE GET THE FILES BACK FROM THE SERVER IF WE AREN'T WRITING THE SERVER IP ADDRESS??**

The browser sends a request to another server, a DNS (domain name system) server which holds a database with domain names corresponding to ip addresses with the domain name, the DNS server will make a 'domain lookup' (will make a query \[search and get\]) for the ip address associated with the domain name you typed and then your browser sends a request to the ip address.

## **WHAT ABOUT HTTPS PART OF THE URL??**

HTTPS stands for Hypertext Transfer Protocol Secure. **WHAT??**

'Hypertext' refers to text documents which contains hyperlinks or links, which makes those documents 'hyper' since they are not totally inanimate. They can refer to other documents. And those documents, you guessed it, are HTML files or other forms of text files.

'Transfer Protocol', intuitive i think, we can understand that it is a protocol or a standard (something or structure that is set and agreed upon and followed) for transferring hypertext.

**WHAT ABOUT SECURE??**

'Secure' means that the transfer process is secured. **YOU HAVE TO BE MORE DETAILED THAN THAT??**

Okay, chill, lets give an example, when you enter your account information (username and password) or card info to a website, you and then click login or pay, you are essentially sending a request to the server with the data. Now, someone might be watching that connection and be able to get the request data that you sent which will include your secret information. Now to avoid this issue, we can encrypt this connection (by TLS protocol or SSL, previously) so that anyone spying will see just encrypted data which he cant decrypt.

## **YOU NEVER TOLD ME ABOUT THE OTHER PARTS OF THE URL.**

One by one, my friend, okay let's talk about it.

'path': a website has many html files, there is the main page and there are other pages, the part after the whole domain name so [`google.com`](http://google.com) gets sent to the server as part of the request under a key value pair (so the request will contain a key-value pair, the key is called 'path' and the value is anything after the whole domain which in case of [`https://www.google.com/`](https://www.google.com/) is the slash `/`, now the JS code on the server analyzes that path value and based on the value will return a specific page, if it finds the path to be just `/` it will return the main page, if it is `/article-501` it will return another html page which hopefully should be a page about article 501 if the developer coded it logically.

'anchor': if you know css, then you would know that `#` is written in front of the element id name in the css file or to form a css selector for that id element, same in js when using querySelector method. When a link is written without an anchor, the browser opens the page at the top (the top part of the page will be the top of the html file) but if there is an anchor, the browser will open the page at the section or element which has an id with the name after the `#` (the top of the page initially will the be the section or element) and you can scroll up or down.

### YOU THOUGHT SO.

I didnt forget, you wanted to know why a domain was called like that. A domain from the name suggests a seperate area from its surroundings, similarly, a domain in the URL suggests that any pages under that domain are of a seperate entity from the larger network of the internet. `google` is a domain name so all pages with the domain google are related and are seperate from other pages of the internet.

---

*This chapter concludes here, and I hope you enjoyed it. If you have any questions, please feel free to ask them below. Additionally, I welcome any corrections or valuable information you may have to contribute.*

*The content of this series draws inspiration from Maximilian Schwarzmüller's Node.js course on Udemy, serving as an index for the topics covered. However, it should be noted that the content reflects my personal interpretation and additional research conducted by me.*