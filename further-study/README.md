# [tktk Module Name] - tktk Microlesson Name

![Hero image](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to tktk

## 15. Further Study

### Turning `NodeList` & `HTMLCollection` Array-Like Objects Into Actual Arrays

As discussed in the lesson, methods designed to return a collection of DOM elements return "array-like" objects that have a `forEach` method, but don't contain other useful methods that full-fledged arrays have.

If you would need to hold your DOM elements in an actual array, either of the following two approaches will do the trick...

#### `Array.from()` Method

Here's how you can use the [Array.from](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/from) static method to convert an iterable, such as a NodeList, into an actual array:

```js
const itemEls = Array.from(document.querySelectorAll('.item'));
```

Now, `itemEls` would be an actual array with all array methods available.

For example, here's how you could find the index of a clicked DOM element in the array:

```js
const itemEls = Array.from(document.querySelectorAll('.item')); // puts all returned elements into an array
const containerEl = document.querySelector('section'); // selects the first <section> tag

containerEl.addEventListener('click', handleClick); // attaches a click listener/handler to the <section> element

function handleClick(event) {
  const indexOfClickedItem = itemEls.indexOf(event.target); // returns the array index of the item clicked
  console.log(indexOfClickedItem);
}
```

❗What is [event](https://developer.mozilla.org/en-US/docs/Web/API/Event)? What is [event.target](https://developer.mozilla.org/en-US/docs/Web/API/Event/target)? The event interface is an extremely useful tool that will help provide us with the properties of the element being acted upon.

#### Spread Syntax

Another way to convert a NodeList or HTMLCollection into an array is by using the [Spread Syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax) within an array literal:

```js
const itemEls = [...document.querySelectorAll('.item')];
```

### Other Methods to Select Multiple Elements

The following methods _can_ also be used to select multiple elements:

- `getElementsByTagName(namesString)`
- `getElementsByClassName(namesString)`

The above methods return a **live** [HTMLCollection](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCollection).

Although it's pretty cool that the returned list is automatically updated to include/exclude DOM elements as the DOM changes, the above methods are not as flexible as the `querySelectorAll` method.

## References

- [Locating DOM Elements using Selectors](https://developer.mozilla.org/en-US/docs/Web/API/Document_object_model/Locating_DOM_elements_using_selectors)

- [Intro to the DOM on MDN](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)
