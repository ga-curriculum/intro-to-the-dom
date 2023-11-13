# ![Intro to the DOM - Modifying an Element](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to select elements from the DOM.

## Modifying text

Now that you can select an element, let's modify its text content.

As we explored the `titleElement`'s properties, you may have seen a couple related to text. The [`textContent`](https://developer.mozilla.org/en-US/docs/Web/API/Node/textContent) property will be our preferred way of interacting with an element's text. It's speedy and avoids some of the pitfalls of other methods of setting text. As a bonus, it has a name that matches what it is - text content. So how do we use it?

```javascript
paragraphElement.textContent = 'The placeholder text is gone!';
```

Adding this to your JavaScript file will cause the text content of the paragraph element to change to the string we've specified: `'The placeholder text is gone!'`

It's important to recognize that this is a property just like any other property; that doesn't change because it is a DOM element. For example, we can console log it:

```javascript
console.log(paragraphElement.textContent);
// prints: 'The placeholder text is gone!"
```

We can even perform logical operations with it:

```javascript
if (paragraphElement.textContent !== '') {
  console.log('The paragraph has text content!');
}
```

## Modifying style

DOM elements have a [style](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/style) property that can be used to set CSS styling!

We can center the text in the `<h1>` by setting the `textAlign` property on the `style` object:

```js
const titleEl = document.querySelector('#title');
titleEl.style.textAlign = 'center';
```

Recall that the naming convention used for CSS properties in CSS is ***kebab-case***. In JavaScript, variable and property names can't include a `-`, so that naming convention can't be used here. That is why we have to use ***camelCase*** property names for CSS properties (like `textAlign` above) instead. 

### 🧠 You Do 

Get some practice setting styling on a DOM element. Change the text color of the `<p>` element to a color of your choosing.
