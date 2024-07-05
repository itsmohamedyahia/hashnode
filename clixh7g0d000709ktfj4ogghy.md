---
title: "Exploring Nodejs: Chapter 2 — URLS AND THE INTERNET"
datePublished: Thu Jun 15 2023 18:30:12 GMT+0000 (Coordinated Universal Time)
cuid: clixh7g0d000709ktfj4ogghy
slug: exploring-nodejs-chapter-2-urls-and-the-internet
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1686853835989/75ce7e9c-5e8e-4f1f-9cbc-46e76eb78de1.png
tags: tutorial, web-development, nodejs, backend, webdev

---

**Chapter 2 is here!** In this chapter, we'll talk about how the internet works, what happens when we go to a URL, the different parts of a URL, and how DNS servers help us traverse the web. Hope you enjoy it!

---

### WHAT HAPPENS UNDER THE HOOD WHEN I ENTER A URL IN THE BROWSER ADDRESS BAR??

Well, you first need to know what a URL is.

**Okay, what is a URL?**

URL stands for "uniform resource locator."

**Why?**

"Uniform" because all URLs have a uniform and standard structure.

"Resource Locator" because a URL is used to locate a file or a "resource" on the internet or even locally on your computer.

**And it consists of some parts, as shown in the image:**

![url constituents](https://upload.wikimedia.org/wikipedia/commons/thumb/b/ba/URL_structure.jpg/800px-URL_structure.jpg?20200419144644 align="left")

> A picture showing URL structure. Illustration made by [Noémie2602](https://commons.wikimedia.org/w/index.php?title=User:No%C3%A9mie2602&action=edit&redlink=1) and licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.en).

Lets focus on the domain for a second. We refer to `wikipedia` as the domain. [`en.wikipedia.org`](http://en.wikipedia.org) can be called the domain name too.

### HEY, WHY IS IT CALLED A DOMAIN??

**Just wait a second, be patient.** That domain, mmm, well, let's get back to that in a second. I get a page back when I enter the URL, **but where is this page stored?**

This page is stored on a computer like the one you're reading from right now. But if that computer's sole purpose is to serve files, then we call it a server. Makes sense, right?

So, I enter the domain part (which is the unique part of a URL, if we're writing something like "[https://www.google.com/](https://www.google.com/)"). And then my browser magically knows that it should get a file from another computer across the internet, **is that it?**

Well, it's not magic once you understand what happens. We have to think first: **how does our browser get to that other computer? They have to be connected, right?** That's right; they are both connected to the "internet."

### **WHAT IS THE INTERNET EXACTLY, IS THAT SOME CLOUD IN THE SKY?**

The internet is much simpler than most people think. It is just wires. Yes, your computer is connected to another computer (server) through a wire unless you are connecting to Wi-Fi, then most of the pathway is wires. If you are connecting to Wi-Fi, that Wi-Fi will be connected to your router, then a modem (or a 3-in-1 device), then to your ISP infrastructure (which is essentially routers). Your ISP is connected to other main ISPs, and there are wires that cross seas and oceans to connect the whole world together! (If you are interested, you can see actual footage of the physical infrastructure of the 'internet' through this [YouTube video](https://www.youtube.com/watch?v=TNQsmPf24go).)

When a computer is connected to a router, it is given an IP address. Your router also has an IP address. Every device connected to the internet has an IP address to identify it from the rest of the devices, just like a home address, so that data traveling across the 'web' or 'internet' or wires knows where to go. To get a file from another computer, you have to request it. Just like in real life, if you want something, you request it. The server then returns a response, which might include the website files.

When you enter an IP address in the address bar, the browser sends a request to the server to fetch the files. The file or files sent back are determined by a set of code that tells the server, "Hey, if you get a certain request, send a certain response." That set of code is the 'backend' and can be written in multiple languages, one of which is JavaScript and will be run by Node.js, the runtime environment.

### **BUT WE ARE NOT WRITING IP ADDRESSES, ARE WE??**

Well, we could, but for convenience, we are writing a URL, the unique part of which is the domain name. **Does a server have a domain name so that we could identify it with?**

No, servers have IP addresses.

**But how do we get the files back from the server if we aren't writing the server IP address?**

The browser sends a request to another server, a DNS (Domain Name System) server, which holds a database with domain names corresponding to IP addresses. With the domain name, the DNS server will make a 'domain lookup' (query) for the IP address associated with the domain name you typed, and then your browser sends a request to the IP address.

### **WHAT ABOUT HTTPS PART OF THE URL??**

HTTPS stands for Hypertext Transfer Protocol Secure. **WHAT??**

'Hypertext' refers to text documents which contain hyperlinks or links. These hyperlinks make those documents 'hyper' since they are not totally inanimate. They can refer to other documents. And those documents, you guessed it, are HTML files or other forms of text files.

'Transfer Protocol,' intuitive I think, is a protocol or a standard (something or structure that is set and agreed upon and followed) for transferring hypertext.

**What about secure?**

'Secure' means that the transfer process is secured. **You have to be more detailed than that?!**

Okay, chill, let's give an example. When you enter your account information (username and password) or card info to a website, and then click login or pay, you are essentially sending a request to the server with the data. Now, someone might be watching that connection and be able to get the request data that you sent, which will include your secret information. Now, to avoid this issue, we can encrypt this connection (by TLS protocol or SSL, previously) so that anyone spying will see just encrypted data, which they can't decrypt.

### **YOU NEVER TOLD ME ABOUT THE OTHER PARTS OF THE URL.**

One by one, my friend. Okay, let's talk about it.

'Path': A website has many HTML files. There is the main page, and there are other pages. The part after the whole domain name, such as [google.com](http://google.com), gets sent to the server as part of the request under a key-value pair. The request will contain a key-value pair where the key is called 'path,' and the value is anything after the whole domain. In the case of [https://www.google.com/](https://www.google.com/), [the value is the slash](https://www.google.com/) (/). The JS code on the server analyzes that path value and, based on the value, returns a specific page. If it finds the path to be just `/`, it will return the main page. If it is `/article-501`, it will return another HTML page, which should be a page about article 501 if the developer coded it logically.

'Anchor': If you know CSS, then you would know that `#` is written in front of the element ID name in the CSS file or to form a CSS selector for that ID element, similar to when using the querySelector method in JS. When a link is written without an anchor, the browser opens the page at the top (the top part of the page will be the top of the HTML file). But if there is an anchor, [the browser will open t](https://www.google.com/)he page at the section or element which has an ID with the name after the `#` (the top of the page initially will be the section or element), and you can scroll up or down.

### YOU THOUGHT SO.

**I didn't forget! You wanted to know why a domain is called that.**

A domain, from the name itself, suggests a separate area from its surroundings. Similarly, a domain in the URL suggests that any pages under that domain are from a separate entity compared to the larger network of the internet.

**For example, Google is a domain name. So, all pages with the domain "google" are related and are separate from other pages on the internet.**

---

*This chapter concludes here, and I hope you enjoyed it. If you have any questions, please feel free to ask them below. Additionally, I welcome any corrections or valuable information you may have to contribute.*

*The content of this series draws inspiration from Maximilian Schwarzmüller's Node.js course on Udemy, serving as an index for the topics covered. However, it should be noted that the content reflects my personal interpretation and additional research conducted by me.*