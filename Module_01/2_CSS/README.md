CSS :nail_care:
================================================================================

*Cascading Style Sheets* is used to style and layout web pages. For example, to change the font, color, size and spacing of your contnet, split it into multiple colomuns, or add animations and other decorative features.

# Syntax
CSS consists of two basic building blocks.
* **properties**: The what. These are the style you want to apply, for instance font, width, background
* **values**: The how. These what you want to set your properties to. For instance the value Helvetica for the font property.

You can apply these properties to an element in the document by specifying a selector.
For instance given the following HTML element:
```
<h1>Hello World</h1>
```
We can select it using the following block of CSS
```
h1 {
  color: gray;
  font: Helvetica;
}
```
We're not going to dive too deep into css syntax or conventions around syntax here. However, if you'd like to read more [this article](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Syntax) from MDN is a great resource.

# Selectors
In CSS selectors are used to target HTML elements. There are a few different
types of selectors. Here we will review some high level concepts, if you'd like
to learn more about the individual selectors this
[MDN link](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Selectors#Selectors_article_overview)
is an excellent resource.

## Selector Types
* **Simple Selectors**: match one or more elements based on class or id. For a
 class prepend `.` before the class name and id prepend `#`. This is the selector
 is the most common and can handle most of your styling needs.

    Example:
    ```
    <div class="foo">Example 1</div>
    <div id="bar">Example 2</div>
    ```
    CSS
    ```
    .foo {
      color: gray;
    }
    #bar {
      color: red;
    }
    ```
* **Attribute Selectors**: match one or more elements based on their attribute(s).
  These will be surrounded by `[]` and can include the attribute and value or just
  the attribute.
    Example:
    ```
    <div data="foo">Hello World</div>
    ```
    both of the following CSS selectors will work
    ```
    [data] {
      color: gray;
    }
    [data="foo"] {
      color: red;
    }
    ```
* **Pseudo-classes**: match one or more elements based on their state. For
  example an element that is being hovered over, or a disabled form element.
  There is a more in-depth explanation of psuedo-classes and elements
  [here](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Pseudo-classes_and_pseudo-elements#Pseudo-classes).
* **Combinators and Multiple Selectors**: These are not a different type entirely
  they allow to select very specific elements within other selectors or by
  combining selectors.
  [Here](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Combinators_and_multiple_selectors)
  is another great resource for more context.

    Example: if I wanted to target only the `<p>` element for content without
    using a class or id
    ```
    <p>Intro</p>
    <div class="foo">
      <p>Content</p>
    </div>
    <p>Outro</p>
    ```
    The following block of css would select it
    ```
    .foo p {
      color: blue;
    }
    ```

# Inheritance and cascade
CSS stands for *cascading style sheets* because the idea of cascading is
important in CSS. This essentially means the order in which we make CSS
declarations is important. What selectors ultimately win depend on 3 factors

1. importance
2. specificity
3. order

### Importance
There is a special syntax you can use to make certain that a declaration will
always win, `!important`. Its best to avoid using `!important` unless its
absolutely necessary, because it can cause problems when your CSS becomes
more complex. In the example below, even though an id selector would win
due to specificity, the `!important` style would win out and both `div`
elements would be gray.

Example:
```
<div class="foo" id="winner">Example 1</div>
<div class="foo">Example 2</div>
```
CSS
```
#winner {
  color: red;
}
.foo {
  color: gray !important;
}
```

### Specificity
This is how specific a selector is. For instance if I want to select a particular
`div` element using the `div` selector might not be a good option if there are
hundreds or thousands of `div` elements in the HTML document. Using a class,
id, or parent element might add the specificity needed to select just one element.

Example:
```
<p class="content">Introduction to CSS</p>
<div class="container">
  <p class="content">Hello World!</p>
</div>
```
CSS
```
.container .content {
  border: solid black 1px;
}
```
Specifying the parent `div` will ensure only the `p` element within it will have
a border property applied.

### Order
Later rules will win out. Take the following example.
```
p {
  margin: 5px;
}

p {
  margin: 0;
}
```
The second declaration will win out because it was declared later.

## Inheritence
In CSS some propeties, when applied to an element, will be inherited by that
elements children. This does not apply to all properties. Generally, it will
make sense when a property is inherited, `font-family` and `color` are inherited
properties. This makes it easy to set things like a font or color in one place
rather than applying it to every element. Properties such as `margin`, `padding`,
and `border` will not be inherited by child elements. You would likely have to
unset a lot of the children if they were.

### Additional Resource
There are more in-depth examples and explanations of cascading and inheritance
explained in this
[MDN Resource.](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Cascade_and_inheritance)

# The Box Model
![box model](https://mdn.mozillademos.org/files/13647/box-model-standard-small.png)

Each element in a document is structured like a layered box. The following properties manipulate these layers.

## `width` and `height`
`width` and `height` are set on the content box. The content box contains an element's content, which could be text or child elements.

There are some other properties, `min-width`, `max-width`, `min-height`, `max-height`. They allow you to control an elements height without having set a hard value, this would allow content to grow or shrink, but only to a set value.

## `padding`
`padding` is the *inner* margin of the CSS box between the content and the border. Setting this can be done on all sides using `padding`, or individual sides using `padding-top`, `padding-bottom`, `padding-left`, and `padding-right` properties.

## `border`
The `border` wraps an element acting as a border. It sits between the padding and margin. The `border` proptery is set to 0 by default, which is not visible. You can set a thickness, style, color using shorthand, for instance `border: 1px solid red`.

You can also manipulate just one part of the border using properties like `border-top`. Additionally, you can change just on property using properties like `border-color`. If you want to be really specific you can apply both a specific side and property with properites like `border-top-style`.

## `margin`
The `margin` is outside of the border. It pushes up against other CSS boxes. It behaves similarly to `padding`, in that you can set all sides with `margin`, or indivdual sides with `margin-left`, `margin-right`, `margin-top`, `margin-bottom`

## Try it out
Try manipulating the boxes in [this sandbox](https://codepen.io/Melizzap/pen/QogaWg?editors=1100) using `padding`, `border`, `margin`, `width`, and `height`. Notice how each property changes how the elements appear.


# How does CSS affect HTML?
We browsers apply CSS rules to a document to affect how they are displayed. A CSS rule is made by:
- A set of `properties`, which have values set to update how the HTML content is displayed.
- A `selector`, which selects elements on the page you would like to apply the property values to

These rule are contained in a **stylesheet**

## Try it out!
Visit this [sandbox](https://codepen.io/Melizzap/pen/XGWgMy?editors=1100)

Try adding these styles to the CSS column
```
h1 {
  background: aqua;
  text-align: center;
}

p {
  border: 2px solid green;
  color: orange;
  padding: 20px;
  text-align: center;
}
```

The first rule starts with the `h1` selector, which means that it will apply all the properties list to every element with the `<h1>` tag.
1. **background** changes the background color of the element
2. **text-align** centers the text

The second rule starts with the `p` selector
1. **border** applies a color, width, and pattern to the border of the element
2. **color** sets the text color
3. **padding** adds space on the inside of the element

Try adding some more styles in the sandbox. [Here is a good resource for CSS properties.](https://developer.mozilla.org/en-US/docs/Web/CSS)

# Applying your CSS to your HTML
## External stylesheet
This is a file with a `.css` extension. It can be referenced in an HTML `<link>` element.

Here is an example of what an HTML file would look like:
```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>My Style</title>
    <link rel="stylesheet" href="style.css"></link>
  </head>
  <body>
    <h1>Hello World</h1>
  </body>
</html>
```
And the CSS file
```
h1 {
  font: Arial;
  color: blue;
}

```

This is often the best method for handling styles, as you can use one stylesheet to style different documents and any updates to the style are contained to this one place.

## Internal stylesheet
Rather than having an external CSS file, you can use the `<style>` element, inside of the HTML head.
An example of an HTML file with an internal stylesheet would look like this:
```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>My Inner Style</title>
    <style>
      h1 {
        background: yellow;
        color: blue;
      }
    </style>
  </head>
  <body>
   <h1>Hello World!</h1>
  </body>
</html>
```

This can be a useful trick for working with a content managemnet system where you can't directly modify the CSS files. However, this method would need to be repeated on every page.

## Inline styles
CSS declarations that affect only one element. They are contained in a `style` attribute:

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>My Inline Style</title>
  </head>
  <body>
    <h1 style="color: blue;border: 1px solid green;">Hello World!</h1>
  </body>
</html>
```
While there are certain times this method will be useful. In general its best to avoid this unless you have a good reason.

# Adding Styles to our index.html
Now that we have some of the basics down. Try applying some styles to your
portfolio. If you're having trouble take a look at the example `index.html`
and `style.css` files in this directory.
