# ![Intro to the DOM - Concepts](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will have a basic understanding of the Document Object Model (DOM).

## What is the DOM?

The [DOM (Document Object Model)](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction) is a data representation of a web page loaded in the browser.

The DOM is a tree-like data structure with the top (root) being the `document` object. It mirrors the tree-like structure of the HTML for a given document. Each element in the DOM is referred to as a node.

![Dom Tree](./assets/dom-tree.png)

JavaScript uses the DOM to access an HTML document and its elements. The DOM has an *application programming interface* or [*API*](https://en.wikipedia.org/wiki/Application_programming_interface) that enables developers to make the UI dynamic by using JavaScript to:

- Add elements to the document.
- Remove elements from the document.
- Change the content of elements.
- Change the attributes of elements.

> 📚 An API, or Application Programming Interface, is a set of predefined rules or methods that enables communication and data exchange between software components, applications, or systems.
> 
> Specifically, the DOM API specifically, is a set of methods and properties provided by web browsers that allow us to interact with and manipulate the structure, content, and attributes of HTML using JavaScript. 

## Why do we use the DOM?

We can make web pages dynamic and respond to user action by manipulating the DOM using JavaScript.

For example, imagine a user is interacting with a small to-do application that looks like this:

![To-Do App One](./assets/todo-app-one.png)

To interact with this app, the user might want to:

- Type the text of the new to-do into an `<input>`
- Click an `<button>` labeled **Add to-do**

![To-Do App Two](./assets/todo-app-two.png)

So what happens next? This is why we use the DOM. For the app to function as the user expects when the button is clicked, the click would trigger a function that performs the following: 

1. Create a new element.
2. Access the text entered into the `<input>` element.
3. Set the content of the new element to that text.
4. Place the new element on the page so that it's visible to the user.
5. Finally, for a better user experience (UX), reset the input by clearing out the current text.

The above steps require our JavaScript app to interact with the DOM.

![To-Do App Three](./assets/todo-app-three.png)