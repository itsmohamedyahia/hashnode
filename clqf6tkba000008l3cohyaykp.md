---
title: "Quirks with 'value' attrib/prop on 'input' element/object"
datePublished: Thu Dec 21 2023 12:37:16 GMT+0000 (Coordinated Universal Time)
cuid: clqf6tkba000008l3cohyaykp
slug: quirks-with-value-attribprop-on-input-elementobject
tags: javascript, web-development, webdev, frontend-development

---

```
<input value='something'>
```


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/0ojimogqjx02vl3ssmwp.png)


If we change the user input (text on ui) to be 'something else', what happens to the attribute value in the html and what happens to the value property on the dom object representing that element?

The property value will change but the attribute value wont change. WHY?

Because if we wanted to reset the user input to the default value attrib value, we wont be able to since with each user input change the attribute value changes and thus the default value is lost


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/namfbnlncccbhvpqwkfm.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/i8zy34ar2jyeq8wh2ore.png)


If we changed the property value, it will change the user input on the ui but it wont change the attribute value for the same reasons.

If we changed the attribute value, there are two behaviors.

If the user input changed from the default attribute value even if we changed it and then wrote the default value back again so its based on change and not equality, then if we changed the attribute value it will not reflect either in the ui nor the dom object.

The reason behind this is that we dont want to lose the user input.

If the user input didnt change at all and we changed the attribute value, then it will reflect in the ui and correspondly in the dom object.

The way to change the attribute value is by using 'setAttribute' method

```
input.setAttribute('value', 'something else')
```

How to reset input to be default attribute value?

```
input.value = input.getAttribute('value')
```
