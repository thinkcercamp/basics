HTML
=======================================================================================
HTML (Hypertext Markup Language) is not a programming language, it is a **markup language** used to tell a web browser how to render the web pages you visit. HTML consists of a series of [elements](https://developer.mozilla.org/en-US/docs/Glossary/Element), which you use to enclose, wrap, or **mark up** different parts of the content to make it appear or behave in a particular manner. The enclosing [tags](https://developer.mozilla.org/en-US/docs/Glossary/Tag) can make a bit of content into a hyperlink to another web page, italicize words, and so on. For example take the following line of content:

```
 My cat is very grumpy
```

If we wanted the line to stand by itself, we could specify that it is a parargraph by enclosing it in a paragraph (`<p>`) element:

```
<p>My cat is very grumpy</p>
```

# Anatomy of an HTML element
![Anatomy of HTML element](https://mdn.mozillademos.org/files/9347/grumpy-cat-small.png)

The main parts of an element are:

1. **The opening tag:** This consists of the name of the element (in this case, p), wrapped in opening and closing *angle brackets*. This states where the element begins or starts to take effect -- in this case where the beginning of the paragraph is.
2. **The closing tag:** This is the same as the opening tag, except that it includes a foward slash before the element name. This states where the element ends -- in this case where the end of the paragraph is. Failing to include a closing tag is a common beginner error and can lead to strange results.
3. **The content:** This is the content of the element, which in this case is just text.
4. **The element:** Opening tag + content + closing tag

### Try it out!
Check out [this list sandbox](https://codepen.io/melizzap-the-bold/pen/wNxEBb?editors=1000) and experiment with some of these elements to see how the browser renders them.
* `h1`, `h2`, `h3`, `h4`
* `div`, `span`, `p`
* `b`, `em`, `i`, `q`

Here are some good resources with in-depth explanations of HTML elements
* https://developer.mozilla.org/en-US/docs/Web/HTML/Element#Text_content
* https://developer.mozilla.org/en-US/docs/Web/HTML/Element#Inline_text_semantics

## Nesting Elements (element-ception)
You can put elements inside of other elements, this is called **nesting**. If we wanted to stay that our cat is **very** grumpy, we could wrap the word "very" in a `<strong>` element, with means the word will be strongly emphasized.

### Good :surfing_woman:
```
<p>My cat is <strong>very</strong> grumpy</p>
```

Make sure that your elements are properly nested: in the example box we opened
the `p` element first, then the `strong` element. Therefore we need to close
the `strong` element before the `p` element.

### Bad :-1:
```
<p>My cat is <strong>very grumpy</p></strong>
```
The elements have to open and close correctly, so they are clearly inside or outside one another. If they overlap like above, then your web browser will try to make a best guess at what you were trying to say, and you probably won't get the format you want. Try to avoid it :sunglasses:.

## Block vs inline elements
There are two categories in HTML which you should know about. They are block-level elements and inline elements.
* **Block-level** elements form a visible block on a page -- the will appear on a new line from whatever content came before it, and any content that goes after it will also appear on a new line.  Block-level elements tend to be structural elements on a page that represent paragraphs, lists, navigation menus, footers, etc. A block-level element wouldn't be nested inside of an inline-element, but might be nested in another block-level element.
* **Inline elements** are those that are contained within block-level elements and surround small parts of the document's content. An inline elemnt will not cause a new line to appear in the document; they normally appear inside of a paragraph of text, for example an `<a>` element (hyperlink) or emphasis elements such as `<em>` or `<strong>`

### Try it out!
Let's go back to our [sandbox](https://codepen.io/melizzap-the-bold/pen/wNxEBb?editors=1000) and try the entering the following two lines of markdown. Notice how they are different.

```
<em>one</em><em>two</em><em>three</em>
<p>four</p><p>five</p><p>six</p>
```

### Notes
1. HTML5 redefined [element categories](https://html.spec.whatwg.org/multipage/indices.html#element-content-categories). These definitions are less ambiguous then what we've described above, its less complicated to conceptualize elements as "block" and "inline"
2. "Block" and "inline" are terms used to describe [css boxes](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Box_model#Types_of_CSS_boxes). They are related by default, but changing the CSS display type does not change the type of the element... This confusing language is part of the reason HTML5 dropped these terms.
3. Here's a list of [block-level elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements) and [inline elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements)

## Empty elements
Not all elements follow the pattern opening tag, content, closing tag. Some elements are just a single tag, which usually embeds or inserts something into the document. A great example of this is the `<img>` element, it embeds an image file onto a page.

### Try it out!
Try putting the following element into our [sandbox](https://codepen.io/melizzap-the-bold/pen/wNxEBb?editors=1000)
```
<img src="https://www.fillmurray.com/300/300" />
```

------------------------------------------------------------------------------------------------------
# Attributes
Elements can also have attributes, which look like this:

![Attribute example](https://mdn.mozillademos.org/files/9345/grumpy-cat-attribute-small.png)

Attributes contain extra information about the element which you don't want to appear in the actual content. In the example above, the `class` attribute allows you to give the element an identifying name that can be targeted with style information and javascript actions.

An attribute should have:
* A space between it and the element name.
* The attribute name, followed by an equal sign.
* An attribute value, with opening and closing quote marks wrapped around it.

### Try it out
`<a>` is an element that stands for "anchor" and will make any content it wraps around a hyperlink. It takes the following attributes
* `href`: the web address that you want the link to point to. eg 'http://thinkcerca.com'
* `title`: extra information about the link. eg "ThinkCERCA Marketing Page"
* `target`: the context which will be used to display the link. For instance `target="_blank"` will display the link in a new tab, if this attribute is omitted the link will open in the current page

Let's go back to our [sandbox](https://codepen.io/melizzap-the-bold/pen/wNxEBb?editors=1000) and build a hyperlink to your favorite site!

## Boolean Attributes
Some attributes can be written without values, these are boolean attributes. They only have one value which is the same as the attribute name. A great example is the `disabled` attribute, if you wanted to create a form with a disabled input field you could do the following.

```
<input type="text" disabled >
```

------------------------------------------------------------------------------------------------------
HTML Document Anatomy
------------------------------------------------------------------------------------------------------
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>My test page</title>
  </head>
  <body>
    <p>This is my page</p>
  </body>
</html>
```

1. `<!DOCTYPE html>`: The doctype. Long long ago, when HTML was new (~1991), doctypes were meant to act as links to the set of rules that the HTML  page had to follow to be considered good HTML. There would be automatic error checking and other useful things. They looked something like this:
```
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
```
  They're not used so much now, and are more a historical artifact taht needs to be included for everything to work as expected `<!DOCTYPE html>` is the shortest string of characters that counts as a valid doctype.
2. `<html></html>`: This element wraps all the content on the entire page, sometimes refered to as the root element.
3. `<head></head>`: This element acts as a container for all the stuff you want to include on the HTML page that isn't the content you are showing to your page's viewers. This includes things like keywords and a page descript that you want to appear in search results. CSS to style the content, which we will learn more about in this module :smile:.
4. `<meta charset="utf-84">`: This element sets the character set your document should use to UTF-8, which includes most characters from the majority of written languages. There isn't a good reason not to set this, it can help avoid problems down the road.
5. `<title></title>`: This element sets the title of your page which will appear in the browser tab, and is used to describe the page when you bookmark/favorite it.
6. `<body></body>`: This element contains all of the content you see rendered on a web page.


------------------------------------------------------------------------------------------------------
Start building your portfolio in HTML
------------------------------------------------------------------------------------------------------
Let's start building out a portfolio using what we have learned so far.

First let's build a directory to house our portfolio in your terminal type the following command
```
$ mkdir portfolio
```

Next let's change the `pwd` to `portfolio/`
```
$ cd portfolio
```

And then create a Home page
(*Naming it index will be helpful when setting up your portfolio in Github, more on that in Module 02*)
```
$ touch index.html
```

Now, open the file in VSCode or your prefered code editor and create and add the base `HTML` structure
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>My ThinkCERCAMP Portfolio</title>
  </head>
  <body>
    <p>Hello World!</p>
  </body>
</html>
```

Head back to your terminal and type the following command
```
$ open index.html
```
This should render your portfolio in your default browser.

We're off to a great start but let's add some more elements. Try adding your name, a picture, and links to your linkedIn and twitter to get started. Don't worry about styles yet, we will cover that next in this module. If you're looking for some insipiration, check out the portfolio.html file in this project.

Once you have a solid home page built, lets build a navbar that can take users to a projects page.

First we'll need to create another html file.
```
$ touch projects.html
```
Then add the basic HTML structure
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>My Projects</title>
  </head>
  <body>
    <ul>
      <li>Project 1</li>
      <li>Project 2</li>
      <li>Project 3</li>
    </ul>
  </body>
</html>
```

Great, now lets head back to `index.html` and add a block-level element
```
<div class="navbar">
  <a href="./projects.html" title="My Projects">Projects</a>
</div>
```

Notice the structure of the value in the `href` attribute. Because these files are in the same directory we can use a relative path instead of a full file path. You can read more on file paths [here](https://www.w3schools.com/html/html_filepaths.asp).

Try adding a navbar in your projects file that navigates users back to the home page. Fill out as much or as little information as you want and start getting excited about adding styles in the next lesson!
