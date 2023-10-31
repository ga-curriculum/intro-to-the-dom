# ![Intro to the DOM - Creating an Element](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to create new elements in the DOM.

## Add elements to the page

So, we can select and modify pre-existing elements, but how do we create elements from scratch? 

We're going to add a new `<h2>` element immediately after the `<p>` element. This `<h2>` element will have the text content of `'Comments section'`.

To add an element inside the `<body>` element, we first select the `<body>` element from the DOM. We can use `querySelector()` for this and specify the body element as the argument:

```javascript
const bodyElement = document.querySelector('body');
console.dir(bodyElement);
```

If all is well, we'll have an element logged in the browser console! Now that we have access to the `<body>` element, we can place an element inside it. First, we'll need to create the element. We can do this with the [`createElement()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElement) method on the `document` object.

```javascript
const h2Element = document.createElement('h2');
```

The `createElement()` method accepts a string argument. This string specifies the type of element that should be created. Since we want to create an `<h2>`, we have passed `'h2'` as a string to this method. This method returns the created element!

We can do anything with this element that we could do to an element we've selected from out of the DOM. For example, we can give it some text content like we originally discussed:

```javascript
h2Element.textContent = "Comments section";
```

Cool! Except it doesn't appear on our page.

It's important to note that this element only exists in our JavaScript application. It does not yet exist as an element you can see on the page in your browser. When an element has been created, but we haven't placed it on the page, we refer to it as being ***in memory***. 

To see it, we need to place it on the page! There are a lot of methods we could use to do this, but we're going to use one of the most common - the [`appendChild()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/appendChild) method that exists on a DOM element. This is why we needed access to the `<body>` element. Let's use its `appendChild()` method to add the `h2Element` to the end of it:

```javascript
bodyElement.appendChild(h2Element);
```

You should now see the `<h2>` we created in the browser! The `<h2>` element has been appended as a child of the `<body>` element.

> ⚠ The `appendChild()` method works by adding the element we've passed to it as the ***last element*** inside of the element we're appending it to. Because the last element inside the body in our HTML is currently the `<p>` element, the `<h2>` element we've added will appear immediately after it. 
> 
> However, if we add more elements to the end of the current HTML document, the `<h2>` element will instead appear after those. You'll see this soon. If you're interested in techniques to place elements more exactly, check out the [Placing Elements Precisely Level Up](../level-up/placing-elements-precisely.md).
