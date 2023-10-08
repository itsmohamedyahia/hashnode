---
title: "[VISUAL] CSS Intro, Syntax & the CSS Cascade"
datePublished: Sun Oct 08 2023 17:26:08 GMT+0000 (Coordinated Universal Time)
cuid: clnhqk06q000a08mw7eef0tiu
slug: visual-css-intro-syntax-the-css-cascade
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1696785962038/27461a7b-cd4c-4e4d-b992-d1fb3e5178ee.jpeg
tags: css, web-development, webdev, html5, beginners

---


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/8gmgiid48dzj9spelumm.png)

## CSS Syntax

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/civ19ota2umrvurumc80.png)


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/1m52kj49w8ji58ilhhw7.png)



![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ifys4wvc7ihe87rvuxnw.png)


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/jivrykq6xrabac93ojbg.png)

## CSS Specificity

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/2soct2xser52aqs1a88b.png)


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ki7v67ytpdhgsixkv9d7.png)


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/vol2qbhm7rexjjkz9xpz.png)

## LINK CSS TO HTML

To write the css in a seperate file, you have to link that file to the html.
In the head element, make a new element called link and write this:

```
<head>
    <link href="styles.css" rel="stylesheet"/>
</head>
```

href attribute specifies the path of the file, if the file is in the same  directory as the html, then you just write the file name.

href stands for hypertext reference and yes the value of that attribute (the path) is a reference to the file.

rel stands for relation and here we are specifying the relation of that file we referenced. Is it a stylesheet  file, a favicon, it is an alternative page in a different language?