# Selecting DOM Elements

![Hero image](../assets/tktkhero-main-subhead.png)

**Learning objective:** By the end of this lesson, students will be able to select elements from the DOM.

## Selecting DOM Elements:

### By its `id`

The [getElementById](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById) method is the most efficient way to select a DOM element if it has an `id` assigned to it (using the `id` attribute).

Let's select the `<h1>` by its `id` and save the reference to the DOM element in a variable named `titleEl`:

```js
const titleEl = document.getElementById('title');
console.log(titleEl);
```

If you wish to explore the element's JS object representation (the DOM), use `console.dir()` instead of `console.log()`.

> Note: When using `getElementById`, be sure not to preface the name of the id with `#`, e.g., `document.getElementById('#title');` will return `null`!

Cool, but how do we select a single element without an `id`?  Let's see...

### By its CSS Selector

The [querySelector(selector)](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector) method is the go-to method for selecting a single element using the power of CSS3's selectors.

The **`selector`** argument is a string that follows the rules of regular CSS3 selectors.

Yes, we can select DOM elements using CSS3 selectors just like we do to target elements for styling!

<details>	
<summary>
❓ What selector would be used to select a <code>&lt;section&gt;</code> element with a class of <code>main</code>?
</summary>
<hr>

**`section.main`**

<hr>
</details>

If the CSS selector provided to `querySelector()` matches multiple elements, it returns the **"first"** matching element, however, it's best to avoid this scenario by using a more specific selector.

If no matching DOM element is found, `querySelector()` will return `null`.

If we were to grab the same element as we did above with the `id` of `title` using the `querySelector()` method, we would do the following:

```js
const titleEl = document.querySelector('#title');
console.log(titleEl);
```

### Caching Elements

In the examples above, when using both `getElementById()` and `querySelector()` methods, we stored the return value, in this case a reference to the DOM element, to a variable. This practice is known as **caching**. It is actually not necessary to **cache** a DOM element to make updates or changes. For example, if we wanted to change the text of the element we were using above, we could do so without caching it:

```js
document.getElementById('title').innerText = 'New Title'
```

However, if we needed to make another change to that same element, we would have query and traverse the DOM again to select the element a second time:

```js
document.getElementById('title').innerText = 'Even Newer Title'
```

Coding your web application in this manner could have an effect on its performance. As mentioned, without storing referencts to DOM elements in variables that will be frequently accessed, your application will have to repeatedly query and traverse the entire DOM to find those same elements over and over.

Caching those elements solves that issue and can significantly inprove the performance of your application.

In addition, caching DOM elements will help to keep your code DRY! Storing references to elements that will be accessed repeatedly will reduce the amount of code you need to write, make your code more readable and ultimately easier to maintain.

You'll get a chance now to practice caching on your own, and then also in a bit, manipulating those elements you have cached.

### 👉 YOU DO: Practice (3 mins)

1. In `index.html`, add a `<p>` tag below the `<h1>` and give it a `class` of `cool`, then...

2. Add some content inside of the `<p>` tag - try typing `lorem [tab]` to emit (using _emmet_) random _lorem ipsum_ text.

3. Use `document.querySelector()` to select the `<p>` element with a class of `cool` and assign it to a variable named `pEl`.

4. Verify that the `<p>` element was selected by logging out `pEl`.

## Text

Now that we're able to select an element of our choosing, let's see how we can change the content of that element...

Inspecting the properties of a DOM element in the console reveals a couple of properties that we can use to read and set its content:

- [innerHTML](https://developer.mozilla.org/en-US/docs/Web/API/Element/innerHTML) - Used to retrieve/set content as an HTML string
- [innerText](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/innerText) - Used to retrieve/set content as plain text

Let's check out changing the content of the `<p>` element by assigning the string **`Comments for <strong>Today</strong>`** first to `innerText`, then to `innerHTML`.

**^^ tktk tktk Maybe include assets showing the results of both using innerText and innerHTML**

As you saw, if you want to include HTML in the content, use `innerHTML`.

The power of `innerHTML` may not be obvious at first, however, the string being assigned can be as complex as you want - containing multiple elements with attributes, etc.

If the string you want to assign does not contain any HTML, assigning to `innerText` is more efficient. This way, JS knows that it doesn't need to scan the string, looking for some HTML to process.

> Note:  There is another property, [textContent](https://developer.mozilla.org/en-US/docs/Web/API/Node/textContent), that is very similar to `innerText` - the primary difference between the two is that: `textContent` returns all text content regardless of (CSS) styling, whereas `innerText` takes any styling into consideration.  For example, `innerText` won't return text that has been hidden using CSS.

## Style

DOM elements have a [style](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/style) property that can be used to set CSS styling!

Check out the CSS properties in the console.

<details>	
<summary>
❓ What naming convention is used for CSS properties in the DOM?
</summary>
<hr>

**lowerCamelCasing**

<hr>
</details>

<details>	
<summary>
❓ What naming convention is used for CSS properties in CSS?
</summary>
<hr>

**kebab-casing**

<hr>
</details>

<details>	
<summary>
❓ Why can't kebab-casing be used for the DOM as well?
</summary>
<hr>

**The DOM is JS so the hyphen would be interpreted as a minus sign**

<hr>
</details>

This is how we can center the text in the `<h1>` by setting the `text-align` CSS property on the `style` object:

```js
const titleEl = document.getElementById('title');
titleEl.style.textAlign = 'center';
```

### 👉 YOU DO: Setting Styling on a DOM Element (1 min)

- Change the `color` of the `<p>` element to a color of your choosing.

## Selecting Multiple Elements

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