# Intro to the DOM - Concepts

![Hero image](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to tktk

## What is the DOM?

The [DOM (Document Object Model)](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction) is the in-memory data structure that represents the browser's web document.

> **tktk tktk Looks like another asset from Jim's imgur. It's not bad, not sure how the team feels about it.**
<img src="https://i.imgur.com/W9ahTXh.png">

As you can see, it's a tree-like data structure with the top (root) being the `document` object. **[tktk tktk This will need to change if the above asset becomes drastically different.]**

<details>	
<summary>❓ What JS data type would each of those nodes be?
</summary>
<hr>

**Nodes most certainly will be JS objects with properties used to get/set information and methods to manipulate the DOM.**

<hr>
</details>

If we type `document` in DevTool's console, we'll see the HTML-centric representation of the document, however, we want to explore the JavaScript data structure that is the DOM.  We can do this by typing `dir(document)` in console and exploring the objects and properties of the DOM.

The DOM has an application programming interface ([API](https://en.wikipedia.org/wiki/Application_programming_interface)) that enables developers to make the UI dynamic by using JavaScript to:

-  Add/remove elements to/from the document
-  Change the content of elements
-  Change an element's styling
-  Listen for events, e.g., when an element is clicked
-  Animate elements

After `index.html` is opened in Chrome, use the keyboard shortcut of `option command J` (macOS) or `ctrl shift J` (Windows) to open Chrome's DevTools.

Click on the **Elements** tab to browse the HTML hierarchy of the DOM.

Let's try out the DevTools by clicking on the `h1` element and using the **Styles** panel to add a CSS property of `color: red;`

**Probably going to need a new image here**
<img src="https://i.imgur.com/RAvgNl0.png" alt="going to need a new image?">

Look closely after the closing `</h1>` tag - you see that _`== $0`_?

That tells us that Chrome has created a variable named `$0` that represents the `<h1>` element in the DOM!

Click on the **Console** tab and let's explore the properties on the `$0` element/object by typing `dir($0)`.

You are now able to explore the `<h1>` element's DOM object - referred to as a **node**.

Now try typing this in: `$0.style.backgroundColor = 'yellow'`

> CSS property names in the DOM are lowerCamelCased because hyphens would be interpreted as minus signs.

## Why do we use the DOM?

Developers make web pages dynamic by manipulating the DOM using JavaScript.

For example, in a To-Do app, a user typically would:

- Type the text of the new to-do into an `<input>`
- Click an `[Add Todo]` `<button>`

The developer certainly would have coded a JavaScript function that would run in response to the button being clicked.

That function would then perform the following:

1. Create a new element, e.g., an `<li>`
2. Access the text entered into the `<input>` element
3. Set the content of the `<li>` to that text
4. Append the new element to the appropriate parent element, e.g., a `<ul>`
5. Finally, for a better user experience (UX), "reset" the input by clearing out the current text

Several of the above steps requires the JS to access existing elements. Let's see how we can select those DOM elements...
