# ![Intro to the DOM - Selecting an Element](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to select an element from the DOM.

## Selecting in the browser

Let's start exploring the DOM with Chrome's DevTools. 

With the `index.html` file open in your browser, open the DevTools:

- In macOS, use `⌘ Command` + `Shift` + `C` 
- In Windows or Linux, use  `Ctrl` + `Shift` + `C`

Click on the **Elements** tab to browse the HTML hierarchy of the DOM.

Look closely after the closing `</h1>` tag - you see that _`== $0`_?

tktk Hunter, screenshot here of the Elements tab with the `<h1>` tag we created in setup selected and the `== $0` highlighted (sorry would do this myself, but I'm in Windows land and Chrome's new DevTools UI hasn't been fully implemented here yet)

That tells us that the browser has created a variable named `$0` that represents the `<h1>` element in the DOM!

Click on the **Console** tab, and let's explore the properties on the `$0` element/object by typing `console.dir($0)`.

You can now explore the `<h1>` element's DOM object - aka the `<h1>` node.

## Selecting with `querySelector()`

That's cool for our initial exploration, but we can't use that in our apps. For that, there is `querySelector()`.

The [querySelector()](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector) method on the `document` object selects a single element using CSS selectors. This means we use the same selectors we would use to target an element for styling!

The `querySelector()` method takes a single string argument. This string should follow the rules of regular CSS selectors. 

Let's try it. If we were to grab the same element as we did above using the `querySelector()` method, we could do the following:

```javascript
const titleElement = document.querySelector('#main-title');
console.dir(titleElement);
```

There are some important points about the code above. Let's discuss them more:

- This will select the element with an `id` of `main-title` using the `querySelector()` method on the `document` object.
- A reference to that element is saved in the `titleElement` variable. 
- Note the variable name we've chosen - `titleElement`. It is beneficial for us to append `Element` to the variable name when working with DOM elements. This helps to distinguish it from other pieces of data in our application just by looking at the variable name. We'll commonly shorten this from `Element` to `El`.
- Note that immediately after we created `titleElement`, we added a `console.dir(titleElement)`. We do this to confirm we have selected the correct element from the DOM. You should ***always*** follow this pattern in your apps.

> ♻ **Repeatable Pattern:** Every time you select an element out of the DOM, you should `console.dir()` it to confirm it is what you think it is!

> ❓ Could we use any other CSS selectors to retrieve this same element?

If the CSS selector provided to `querySelector()` matches multiple elements, it returns the first matching element from the document. You should avoid this scenario by using a more specific selector that only matches one element when possible.

If no matching DOM element is found, `querySelector()` will return `null`.

### Caching elements

In the example above, we stored the result of `document.querySelector('#main-title)` to a variable (`titleElement`). We'll commonly refer to that variable as a *cached element reference*. That sounds fancy, but it means that we don't need to query the DOM repeatedly for the same element. When we want to interact with it, we use the variable.

> Creating *cached element references* is a technique in which a DOM element is stored in a variable for future use, minimizing the need to query the DOM to access the same element repeatedly.

This is important for a few reasons:

- We can write less code.
- Querying for elements in the DOM is prone to errors. Doing it less avoids some of those errors.
- It improves performance (querying for elements in the DOM is relatively slow).

### 🧠 You Do

1. In `index.html`, add a `<p>` tag below the `<h1>` and give it a `class` of `"cool"`.

2. Add some content inside the `<p>` tag. To do this quickly, try typing `lorem`, then hit `Tab` on your keyboard to insert placeholder text.

3. Use `document.querySelector()` to select the `<p>` element with a class of `cool` and assign it to a variable named `paragraphElement`.

4. Verify that the `<p>` element was selected by logging out `paragraphElement`.

## ❓ Review Questions

Use the following code to answer the below questions:

```html
<body>
  <h1>My Website</h1>
  <section id="main">
    <h2>My favorite things</h2>
    <ul id="fav-things" class="list">
      <li>Ducks</li>
      <li>Penguins</li>
      <li>Toucans</li>
    </ul>
  </section>
  <section id="secondary">
    <h2>Things I don't like</h2>
    <ul id="bad-things" class="list">
      <li>Spiders</li>
      <li>Snakes</li>
      <li>Snakes</li>
    </ul>
  </section>
</body>
```

1. What selector could you use to select the `<h1>` element?
2. What selector could you use to select the `<section>` element with an `id` of `"secondary"`?
