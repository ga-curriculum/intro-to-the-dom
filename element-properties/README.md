# [tktk Module Name] - tktk Microlesson Name

![Hero image](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to tktk

## 9. Accessing/Modifying the Attributes of an Element

You may need to get, set, or check if an element has a certain **attribute**.

The following are methods that the [Element API](https://developer.mozilla.org/en-US/docs/Web/API/element) has for working with an element's attributes:

- [getAttribute(name)](https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttribute)
- [setAttribute(name, value)](https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttribute)
- [hasAttribute(name)](https://developer.mozilla.org/en-US/docs/Web/API/Element/hasAttribute)

### 👉 YOU DO: Attributes (5 mins)

1. In `index.html`, add an `<a>` element to `index.html` with content of "Visit Google" but **without an `href` attribute**.

2. Reload the page and verify that the link does not work. In fact, it won't even look like a link.

3. In the JS, write the line of code that will add an `href` attribute that will make the link navigate to "https://www.google.com".

> Hint: Which of the attribute methods above looks tasty?

## 10. The `class` Attribute

Technically, you could use those attribute methods above to work with an element's classes.

However, the [classList](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList) property offers a better approach. 

`classList` is an object with the following methods pertaining to classes:

- `add(className, className, ...)` 
- `remove(className, className, ...)`
- `toggle(className)`
- `contains(className)`
- `replace(oldClass, newClass)`

### ❓ Review Questions

<details>
<summary>
(1) If we want to change the text (without HTML) inside of a <code>&lt;div&gt;</code>, which property should we assign to?
</summary>
<hr>

**innerText**

<hr>
</details>

<details>
<summary>
(2) How many DOM elements are returned by the <code>querySelector</code> method?
</summary>
<hr>

**one**

<hr>
</details>

<details>
<summary>
(3) What DOM element property is used to style a DOM element using JS?
</summary>
<hr>

**`style`**

<hr>
</details>

## 11. Selecting Multiple Elements

Before we check out selecting multiple elements, let's add the following HTML below the existing `<p>` element.

VS Code includes [Emmet](https://docs.emmet.io/abbreviations/syntax/), which is a great tool for quickly generating markup. Type the following to generate most of the desired markup below:
<br>`ul#comments>li{comment}*3`

```html
<ul id="comments">
  <li>first comment</li>
  <li>second comment</li>
  <li>third comment</li>
</ul>
```

Like `querySelector()`, the [querySelectorAll(selector)](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll) method uses the power of CSS3 selectors to specify which DOM elements we want to select.

Of course, like the name says, it selects **all** DOM elements that match the provided selector.

### 👉 YOU DO: Selecting Multiple Elements (2 mins)

1. Use `document.querySelectorAll()` to select all `<li>` elements that are children of the element with an id of `comments`, assigning them to a variable named `commentEls`.

2. `console.log(commentEls)` to verify it worked. 
