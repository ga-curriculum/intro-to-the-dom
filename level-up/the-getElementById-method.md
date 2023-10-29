# ![Intro to the DOM - Level Up - The getElementById() Method](./assets/hero.png)

The [getElementById()](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById) method is the most computationally efficient way to select a DOM element but requires that an element has an `id` assigned to it (using the `id` attribute).

Let's select the `<h1>` by its `id` and save the reference to the DOM element in a variable named `titleElementById`:

```js
const titleElementById = document.getElementById('main-title');
console.dir(titleElementById);
```

> ⚠ When using `getElementById()`, be sure not to preface the name of the id with `#`. For example, `document.getElementById('#main-title');` will return `null`!
