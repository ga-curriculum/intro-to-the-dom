# ![Intro to the DOM - Working with Collections of Elements](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to select multiple elements out of the DOM simultaneously and iterate through those elements to carry out actions on them.

## Selecting multiple elements

Before we check out selecting multiple elements, let's add the following HTML below the existing `<p>` element so that we have multiple elements to select!

```html
<ul id="comments">
  <li>first comment</li>
  <li>second comment</li>
  <li>third comment</li>
</ul>
```

Like `querySelector()`, the [`querySelectorAll()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll) method uses CSS selectors to specify which DOM elements we want to select. 

Like `querySelector()`, the `querySelectorAll()` method takes a single string argument. This string should follow the rules of regular CSS selectors. Instead of only selecting the first match, like `querySelector()`, it will select all the found matches.

### 🧠 You Do

Try to select multiple elements out of the DOM!

1. Use `document.querySelectorAll()` to select all `<li>` elements that are children of the element with an id of `comments`, assigning them to a variable named `commentElements`.

2. `console.log(commentElements)` to verify it worked. 

## Iterating over a collection of elements

As you can see, `querySelectorAll` returns an array*, which we can iterate through. Because `querySelectorAll()` always returns this data structure, we will always pluralize the variable name. That's why we called this variable `commentElements` instead of `commentElement`.

We could use a `for` loop or a `for...of` loop to iterate over `commentElements`, but for the most part, we'll stick to `forEach()` loops.

Let's add the following `forEach()` loop in the console to print the text content of each element:

```js
commentElements.forEach((commentElement) => {
  console.log(commentElement.textContent);
})
```

> 🧠 *`querySelectorAll()` doesn't return a true array, but instead something called a `NodeList`. This technical distinction won't impact our normal interaction with them, but if you'd like to learn more or are trying to do something atypical, it may be worth checking out the [`NodeList` Level Up](../level-up/nodelist.md).

### 🧠 You Do

Use the `forEach()` method to modify the styling of each comment element.

Inside the loop, change the font size of every `<li>` element to `30px`.

> Hint: You must use a string like `'30px'` - just the number `30` or the string of `'30'` will not work. 

## ❓ Review Questions

Assuming you are using `querySelectorAll()`, use the following code to answer the below questions:

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

1. What selector could you use to select all the `<h2>` elements?
2. What selector could you use to select all the `<ul>` elements?
