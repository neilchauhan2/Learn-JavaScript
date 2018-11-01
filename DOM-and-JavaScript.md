# DOM & JavaScript

Being a front end developer, it's going to be lot about interacting with DOM Elements, the different HTML elements on the page and changing them via JavaScript that's all encompassed by the DOM, which stands for the Document Object Model. The following model is created by the browser when a web page is loaded and in graphical form, it looks something like a tree of elements or nodes, which is meant to represent every single HTML element on your page.

Let's say, you have a basic HTML code this way:

```html
<html>
  <head>
    <title>Title</title>
  </head>
  <body>
    <h1>Heading</h1>
    <p>Paragraph</p>
  </body>
</html>
```

Now the DOM tree for the above code looks something like the following, built by the browser's rendering engine:

![DOM Tree](https://i.imgur.com/C9vnVHp.png)

It looks something like the above, where there is the root parent element at the top and the children are nested beneath those. Programmatically, what this model allows us to do in JavaScript is, interact with this DOM tree and do things with it. Some of them are:

* We can change or remove HTML elements in the DOM or on the page
* We could change and add CSS styles to these elements via the DOM
* We can also read and change element attributes, say, `href` attribute on anchor tags
* We can also create new HTML elements and insert them into the DOM or the page via JavaScript
* We can attach Event Listeners to different elements like Click events, Key Press events, and Submit events and react to those as well in JavaScript
