# [tktk Module Name] - tktk Microlesson Name

![Hero image](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to tktk

## What is the DOM?

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