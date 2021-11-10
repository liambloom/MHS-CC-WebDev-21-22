# Computer Club Web Development Track

### What is this document?
This document contains all the information you need to catch up if you joined the web dev track later in the year or if you miss a meeting.

### What is Web Development?
Web Development is programming to make websites. You are all familiar with websites. It is quite likely that you are viewing this on a website right now! This is what we’re learning to make.

### Programming Languages
Computers don’t read English, they read programming languages (which, lucky for us, are mostly based on English). Websites are programmed using three programming languages (well, technically they’re not programming languages, but they are languages read by the computer, so close enough).
HTML, or Hyper-Text Markup Language, is the first language we will learn for web development. It is what makes the page. Think text, buttons, images, etc.
CSS, or Cascading Style Sheets, is what is used to style an HTML page. Think fonts, colors, layout, etc.
Javascript, or JS for short, makes the page do stuff. Anything interactive on a web page is almost certainly programmed in javascript. (Note: Java is another popular programming language. Java and javascript are completely unrelated.)

#### A quick note for people who know other languages (like java)

One thing that makes web languages different from most other languages is how they handle errors. In most languages, if you make a mistake, your program won't run, or even compile, but this is not the case for web languages. In web languages, the computer will try to guess what you meant, and if it can't figure it out, it will sometimes ignore the broken piece of code and move on. 

For example, in java, if you forget a semicolon, your program will not even compile. Javascript also uses semicolons, in the same places you would use them in java, but in js, if you forget a semicolon, the computer will simply guess where you *meant* to put a semicolon, and read your code as if there is one there. Usually, it will guess right, but not always.

## HTML

### File Extension

HTML Files use the .html or .htm file extensions. 

### Syntax

#### Tags

An HTML document is composed of **tags**. A tag begins with the `<` sign and ends with the `>` sign. In between those two signs is the name of the tag. So, for example, the `p` tag, which denotes a paragraph, would look like this: `<p>`. When the computer sees that, it knows that this is the beginning of a paragraph. 

To end the paragraph, you use a **closing tag**. A closing tag looks just like the opening tag (for now), except that it has a `/` before the name. A closing paragraph tag would look like this: `</p>`. When the computer sees this, it knows this is the end of a paragraph.

Anything in between the opening and closing tags is the content of whatever it is. So anything between a `<p>` tag and a `</p>` tag is a paragraph. So, the example code:

```html
<p>This is a paragraph</p>
<p>This is another paragraph</p>
```

Would be rendered like this:

> This is a paragraph
>
> This is another paragraph

Altogether, the tags and content are known as an **element**&mdash;in this case, a paragraph element. The above code example has two paragraph elements.

#### Comments

It is sometimes useful in code to write a note to yourself or a fellow programmer. But we don't want the computer to be reading these notes, we only want it paying attention to the code. For this, we have **comments**.

In HTML, a comment begins with `<!--` and ends with `-->`. Anything between those two is ignored by the computer. So the following code

```html
<!-- This is a comment -->
<p>This is a paragraph<!-- This is another comment --></p>
<p><!-- Comments are super useful! -->This is another paragraph</p>
<!-- Comments can also be
    multiple lines! -->
```

is equivalent to the earlier example.

You can put comments pretty much anywhere, but there is one exception. You can't put a comment inside a tag. So the following code won't work:

```html
<p <!-- Uh oh! -->>This is a paragraph</p>
```

The computer will not ignore that comment, and will be very confused.

#### Required elements

There are certain elements that are required in an HTML document. Here is a web page that contains all the required elements. After the example, I will explain what all of them mean.

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title>Simple HTML Page</title>
    </head>
    <body>
        <!-- This is where the content of the page goes -->
    </body>
</html>
```

##### `!DOCTYPE`

White this looks like a tag, it isn't actually one, it's just information for the browser: it tells the browser what version of HTML we are using. `<!DOCTYPE html>` tells the browser that we're using HTML 5. If we wanted to use HTML 4 (which you will probably never have any reason to) you would put `<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">` instead. Although the browser will *usually* be able to figure it out even if you forget this tag, you should still always put this at the top of your HTML pages (if you put it somewhere else, it will break).

##### `<html>`

SGML markup languages (such as HTML), can only have one top-level, or root, element. Top-level elements are elements that are not inside another element. In HTML, this element is the `<html>` element, and everything must go inside it.

##### `<head>`

The head contains information about the document that users don't need to see, but might be helpful to the browser. Examples of things included in the head are the title, metadata, and links to external resources.

##### `<meta>`

The meta tag has metadata&mdash;information about the page. You will notice that there is no closing meta tag (`</meta>`). This is because meta is a **self-closing tag**. Self-closing tags are tags that have not content, and therefore they only have the opening tag. The image tag, `<img>` is another example of a self-closing tag.

You will also see that it has more than just the tag name within the tag. This is called an **attribute**, and it will be explained [later](#attributes-the-anchor-tag).

The meta tag can contain lots of different types of information, such as author and search keywords. What we're using it for here is to tell the browser the charset of our page (you don't need to understand what this means). Like the doctype, the browser will *usually* be able to figure it out if you forget this, but in some cases leaving this tag out can result in garbled text.

##### `<title>`

The title tag contains the title of our page. The title element does not affect what is displayed on the page in any way, the title is only what is displayed on the tab menu. We will learn how to put stuff on the page later.

##### `<body>`

The body is where the contents of our page go. Anything that the user can see is in the body. Anything outside the body is invisible to the user. So, in an actual html page, if we wanted to put a paragraph, we would put it in the body.

#### Attributes + The Anchor Tag

As you saw with the meta tag, sometimes, tags have more information in them than just the tag name. This information is called attributes. An attribute has the following syntax: `attributeName="attribute value"`. The attribute name is one word, *without any spaces*. After that is an equals sign, followed by the attribute value, which is in double quotes. The attribute name *can* have spaces.

One place where this would be used would be the anchor tag `<a>`. This tag allows you to use hyperlinks, which are links that the user can click on to go to another page ([this](https://youtu.be/dQw4w9WgXcQ) is an example of a hyperlink). In order to tell the browser where the hyperlink is linking to, we use the `href` attribute (href stands for Hypertext REFerence). So, to link to [example.com](http://example.com/), we would set the `href` attribute equal to the *full url* of the page we want to link to, like this:

```html
Click <a href="http://example.com/">here</a> to visit example.com!
```

Which renders as:

> Click [here](http://example.com/) to visit examp<span>le.</span>com!

*Again, you* MUST *put the* full url *to the page you want to link to, including the `https://`, and the `www.` if it's there. If you don't do this, it won't work.*

You can also have multiple attributes. For example, to tell an anchor tag to open a link in a new window or tab, you would set the `target` attribute to `_blank`. Here's what that would look like:

```html
Click <a href="http://example.com/" target="_blank">here</a> to visit example.com!
```

> Click <a href="http://example.com/" target="_blank">here</a> to visit examp<span>le.</span>com!

### Other Things:

Other useful, though not as vital, things we've learned about are

- [Headings](https://www.w3schools.com/html/html_headings.asp) (different from head*er*s)
- [Images](https://www.w3schools.com/html/html_images.asp)
- [Lists](https://www.w3schools.com/html/html_lists.asp)
- [Tables](https://www.w3schools.com/html/html_tables.asp) (without CSS these look quite ugly)
- [`<div>`](https://www.w3schools.com/tags/tag_div.ASP) (used mainly for CSS)


## CSS

### The style element

In HTML, there are two very special elements: `<style>` and `<script>`. These are special because the stuff inside of them is *not* HTML. Instead, the `<style>` element contains CSS and the `<script>` element contains javascript. 

The `<style>` element goes in the head of the html document. The contents of the tag are CSS. Here is a demonstration:

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title>My First CSS Page</title>
        <style>
            /* Stuff inside here is CSS, not HTML */
        </style>
    </head>
    <body>
        <!-- ... -->
    </body>
</html>
```

Any CSS code, such as that in this section, goes inside the `<style>` element.

### Comments

As you may have noticed in the example above, comments in CSS are not denoted using `<!--` and `-->`. Instead, CSS comments begin with `/*` and end with `*/`.

*A note for those of you know know java: You many recognize this notation for comments, as it is the same as the notation for multi-line comments in java. You may also be wondering if the java notation for single line comments (`//`) works in CSS. Unfortunately, it does not.*

### Syntax

#### Rules

CSS is made up **rules**, which have the following syntax:

```css
selector {
    property: value;
    property: value;
    property: value;
    /* ... */
}
```

#### Selectors

The first part of a rule, as you may have noticed, is the **selector**. There are many things that can be selected for in a CSS selector, but the one we'll focus on for now is selecting for tags. To select all elements of a particular tag in html, you simple use the name of the tag. So, to apply a rule to all paragraphs in an HTML page, we would do the following:

```css
p {
    property: value;
    property: value;
    property: value;
    /* ... */
}
```

After the selector is a pair of curly brackets `{}`, which contain all of the properties to apply to the selected elements.

#### Properties

Properties are what is set in CSS. There are hundreds of properties in CSS, so I will not be going over them all in this document.

To set a property, you put the name, followed by a colon, followed by the value, followed by a semicolon. If you do not have a semicolon, the computer will think that the next property is part of the value of this property, and it will get very confused.

One property is the `background-color` property, which, as you can probably guess from the name, sets the background color of an element. To make the background of your page red, you would use the following CSS:

```css
body {
    background-color: red;
}
```

To control text color, we use the `color` property. So, if we wanted to make a page with a black background and white text, we would write the following:

```css
body {
    color: black;
    background-color: white;
}
```

The order you put the properties in doesn't matter unless you have more than one that affects the same thing, e.g. `margin` and `margin-left`, in which case the latter is given higher precedence.

### More Selectors

#### IDs

IDs can be used to select a specific element in an HTML page, rather than all elements of a particular type. To set an element's id, use the `id` attribute, like this:

```html
<p id="my-paragraph">Text here</p>
```

And then selected using `#`

```css
#my-paragraph {
    /* ... */
}
```

IDs should be unique and they cannot contain spaces.

#### Classes

Classes in CSS are different from classes in java. CSS classes are used to apply a rule to certain elements. You can apply any class to any element. Classes are set in HTML using the `class` attribute:

```html
<p class="highlighted">Highlighted text here</p>
```

And selected using `.`

```css
.highlighted {
    background-color: yellow;
}
```

An HTML element can have multiple classes, separated by spaces (`class="first-class second-class"`). A single class can apply to many elements.

#### Combining Selectors

There are many ways to combine selectors, but the only one we've used so far is the comma `,`, which is used to select for multiple things. For example

```css
td, th {
    /* ... */
}
```

is a rule that applies to all `td` and `th` elements.

### Precedence

CSS Precedence is somewhat confusing. I will try to explain it here.

CSS applies outer elements, then inner elements, so the inner elements' style's have higher precedence. For example, in our previous page with black text, links would still be blue, because the styles which apply to the `<a>` tag, which is inside the `<body>` tag, take higher precedence. Since the `<a>` tag has `color: #0000EE;` by default (this CSS is built into the browser and is applied to every web page), the link is blue (`#0000EE` is a [color code](https://www.pluralsight.com/blog/tutorials/understanding-hexadecimal-colors-simple))

If multiple selectors apply to the same element, then the following is the order of precedence:

1. A CSS property with `!important`. E.g. `p { color: red !important; }` (You should usually not use this)
2. [Inline CSS](https://www.w3schools.com/tags/att_style.asp) (You should ~~almost~~ never use this)
3. Rules that select by ID
4. Rules that select by class, [attribute](https://www.w3schools.com/css/css_attribute_selectors.asp), or [pseudo-class](https://www.w3schools.com/css/css_pseudo_classes.asp)
5. Rules that select by element or [pseudo-element](https://www.w3schools.com/css/css_pseudo_elements.asp)

If there is still a tie, then the rule that is declared later takes precedence.

### External CSS Files

If you have ever used a website, you will probably have noticed that many pages on that website look similar. This is because they all use the same CSS. It would be incredibly impractical to copy and paste our `<style>` element to every single page, especially as our styles get longer (for reference, the homepage of google has 671 CSS rules, each of which has several properties). To solve this problem, we can put css into its own file, and link it in each of the HTML pages that we want to use it in.

To create a CSS file, create a new file with the .css file extension. In it, put all of your style rules. This is *not* html, the `<style>` tag does not appear in the css file.

To link a CSS file, we use the `link` tag, which goes in the head. It has two attributes that are relevant to us: `href` and `rel`.

The `href` attribute, which you may recognize from earlier, when we talked about the anchor tag, tells the browser where the file is. In this case, we don't need to use `http://` because we can use a **relative path**. Relative paths mean that your computer looks for the file relative to the html. So, if your html and css files are in the same directory (a directory is just a fancy name for a folder), then you can just up the name of the file. 

The `rel` attribute is used to tell the computer what we're giving it. This is important because the `link` tag can be used to link other things besides stylesheets. In this case, we would set `rel` to `stylesheet`. 

We put this link tag in the head to link to a stylesheet. An example link tag would be:

```html
<link href="my-styles.css" rel="stylesheet">
```

As you may have noticed, the link tag is self-closing, because it has no content.

## Javascript

We have not yet started learning about javascript

&#127881;&#127881; **CONGRATULATIONS!** You've successfully learned the fundamentals of web development.
