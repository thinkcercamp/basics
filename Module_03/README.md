# Basic JavaScript

# Under the Hood
When a browser displays a document, it is a combination of the content and style information. Two things are happening
1. The browser converts HTML and CSS into the *Document Object Model* (DOM). The DOM represents the document in the computer's memory, a combiation of content and style.
2. The browser displays the contents of the DOM

![DOM model](https://mdn.mozillademos.org/files/11781/rendering.svg)

# The DOM
Every element in the HTML markup becomes a **DOM node**. Nodes are defined by their relationship with other nodes. Together, the nodes form the tree-like DOM structure. Some nodes have parents, child, and siblings. Understanding the DOM will help in maintaining and debugging CSS.

### This HTML code
```
<div>
  <p>Foo</p>
  <p>Bar</p>
  <p>Baz</p>
</div>

```

### Translates to this DOM Tree
```
div
|-p
| └─ "Foo"
|-p
| └─ "Bar"
|-p
| └─ "Baz"
```

## Try it out
[Go back to our sandbox](https://codepen.io/Melizzap/pen/XGWgMy?editors=1100) and see what it looks like in the browser.

Now, try adding some styles:
```
p {
  border: 1px solid black;
  background: peachpuff;
}
```

The browser will parse the HTML and create the DOM, then parse the CSS and apply it to the DOM. Since we're only applying style properties to the `p` selector. That is the only change we will see.



### Learn Javscript

Below are two resources that are good for getting started with Javascript. The content overlaps, but it wouldn't hurt to do both. The second is a little more in depth, but might be easier to work through if you 

We'll have a tutorial showing you how to use some of this knowledge on your portfolio soon, but this is a good introduction to the basics of Javascript that will prepare you tuse it in the browser.

**Interactive Course**

Introduciton to Javascript Section 1-9 (Introduction through Classes)

<https://www.codecademy.com/learn/introduction-to-javascript>

**Online Book**

Eloquen Javascript Ch. 1-5

<https://eloquentjavascript.net/>
