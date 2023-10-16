# Element Properties

![Hero image](../assets/tktkhero-main-subhead.png)

**Learning objective:** By the end of this lesson, students will be able to manipulate the attributes of an element.

## Accessing/Modifying the Attributes of an Element

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
