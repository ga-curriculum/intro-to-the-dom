# Collections of Elements

![Hero image](../assets/tktkhero-main-subhead.png)

**Learning objective:** By the end of this lesson, students will be able to tktk

## Iterating Over a Collection of Elements

`querySelectorAll` returns an array-like object called a [NodeList](https://developer.mozilla.org/en-US/docs/Web/API/NodeList).

There are three approaches we can use to iterate over the elements in a NodeList:

1. **A regular [for](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for) loop**:  This works, but it's not as readable or elegant...

2. **The NodeList's [forEach](https://developer.mozilla.org/en-US/docs/Web/API/NodeList/forEach) method**:  A good option when you want to iterate through **all** elements and/or need to access the **index** of the iteration.

3. **A [for...of](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of) loop**:  Elegant and allows early exit of the loop with the `break` statement.  However, if we need to access the **index** of the iteration, we would need to track it manually by initializing a separate variable before the loop and incrementing it within the loop.

Let's type the following `for...of` loop in the console to log each element:

```js
for(let commentEl of commentEls) {
  console.log(commentEl);
}
```

Now let's use the same `for...of` statement to modify those comment elements...

### 👉 YOU DO: Iterating and Updating Styling (3 mins)

- Add a `for...of` loop to `main.js` that changes the font size of all the `<li>` comment elements to `30px`.

  > Hint: You must use a string like `'30px'` - just the number `30` or the string of `'30'` will not work. 

## 14. ❓ Essential Questions (3 mins)

<details>
<summary>
(1) What method is the most efficient for selecting an element that has an <code>id</code>?
</summary>
<hr>

**`getElementById`**

<hr>
</details>

<details>
<summary>
(2) If we want to assign content to an element that includes HTML, what property on the DOM element would we assign to?
</summary>
<hr>

**`innerHTML`**

<hr>
</details>

<details>
<summary>
(3) If we want to assign plain text (no embedded HTML), what property on the DOM element would we assign to?
</summary>
<hr>

**`innerText` (or `textContent`)**

<hr>
</details>

<details>
<summary>
(4) Which property on a DOM element is used to set the CSS styling for that element?
</summary>
<hr>

**`style`**

<hr>
</details>
