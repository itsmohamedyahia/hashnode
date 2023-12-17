---
title: "HTML Collection vs Nodelist"
datePublished: Sun Dec 17 2023 11:19:49 GMT+0000 (Coordinated Universal Time)
cuid: clq9eakfd000208lie81eaowk
slug: html-collection-vs-nodelist
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1702811979683/527332fe-1226-495c-8612-7fec0828e200.png

---

Both are array-like objects but they differ in some areas

##### HTML Collection

- is a collection of element nodes
- is returned by 'getElementsByClassName' and 'getElementsByTagName'

#### Nodelist

- contains all types of nodes: element nodes, text nodes, etc
- is returned by 'querySelectorAll'

====

NodeList returned by querySelectorAll is static. Static means that it doesnt get updated if more items that match the query are added, removed, modified. It doesnt mean that updating properties of an item inside a nodelist wont be reflected.

```html
<html>
  <p class="luck">easy mate</p>
  <p class="luck">easy bait</p>
  <p class="luck">easy late</p>
</html>
```

```js
const pEls = document.querySelectorAll("p");
console.log(pEls); // {p, p , p}
document.querySelector("html").appendChild(document.createElement("p"));
console.log(pEls); // {p, p , p}
```

so it didnt get added to the node list but if we did the same but used `getElementsByTagName` it would get reflected and we would see the fourth p added to the html collection
