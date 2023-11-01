# ![Intro to the DOM - Element Attributes](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to manipulate the attributes of an element.

## Accessing and modifying the attributes of an element

You may need to get, set, or check if an element has a certain attribute. As a reminder, in this code snippet, `id` and `class` are both attributes:

```html
<h1 id="main-title" class="title">Intro to the DOM</h1>
```

The following methods enable us to work with an element's attributes:

- [`getAttribute()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttribute)
- [`setAttribute()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttribute)
- [`hasAttribute()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/hasAttribute)
- [`removeAttribute()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/removeAttribute)

These attributes can be useful when carrying out logic in an app. To see this in action, add a button to your HTML:

```html
<button disabled>Click me!</button>
```

> 💡 `disabled` is a boolean attribute that doesn't have a value. If it's present on an element, then that element cannot be modified or interacted with by a user.

Then, use `querySelector()` to get this element from the DOM:

```javascript
const buttonElement = document.querySelector('button');
```

Let's add a check to see if the button has the `disabled` attribute. If it does, let's remove it.

To see if an element has an attribute, we'll use the `hasAttribute()` method. It accepts a single string argument. If it has the attribute we specify with the string argument, it will return `true`. Otherwise, it will return `false`. 

```javascript
if (buttonElement.hasAttribute('disabled') === true) {
  // the button has the disabled attribute
}
```

We can then remove the `disabled` attribute with the `removeAttribute()` method. It accepts a single string argument. If it has the attribute we specify with the string argument, it will be removed.

```javascript
if (buttonElement.hasAttribute('disabled') === true) {
  buttonElement.removeAttribute('disabled');
}
```

We can now click the button! It still doesn't do anything, but at least we can interact with it!

### 🧠 You Do

Test out the `setAttribute()` method. It accepts two arguments - the first is the attribute we would like to change, and the second is the value we would like to change it to. Check out the [documentation for `setAttribute()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttribute) to help you out.

Give the `buttonElement` we created above an `id` of `'submit'`.

Inspect the element in the DevTools to confirm that this was successful.

## The `class` attribute

Technically, you could use those attribute methods above to work with an element's classes. However, the [`classList`](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList) property offers a better approach because it has methods built specifically for interacting with classes.

`classList` is an object with the following methods pertaining to classes:

- `add(className, className, ...)` 
- `remove(className, className, ...)`
- `toggle(className)`
- `contains(className)`
- `replace(oldClass, newClass)`

Let's add a class called `'btn'` to the `buttonElement`. The `classList`'s `add()` method accepts any number of comma-separated strings. Each one will be added to the element's class!

```javascript
buttonElement.classList.add('btn')
```

Inspect the element in the DevTools to confirm that this was successful.

### 🧠 You Do

Following the examples in the [`classList` documentation](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList), write some code to get rid of the `'btn'` `class` from the `buttonElement`, then give it a new `class`: `action-button`

Inspect the element in the DevTools to confirm that this was successful.
