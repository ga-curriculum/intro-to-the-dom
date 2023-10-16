# Intro to the DOM - Setup

![Hero image](../assets/tktkhero-main-subhead.png)

**Learning objective:** By the end of this lesson, students will be able to have a basic understanding of what the DOM is and create new directories and files for HTML and JS to practice DOM concepts, fundamentals, and manipulation.

**> tktk Going by the Current Competency Map, I have the 'What is the DOM?' section included here in Setup. I think it does work here, just wanted to discuss whether Setup is also for basic concepts, as in setting up the concepts, or we just want to have Setup be setting up of the code. Depending on how we want to go, this will either stay here or move to Concepts.**

## What is the DOM?

The [DOM (Document Object Model)](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction) is the in-memory data structure that represents the browser's web document.

**vv [tktk tktk Looks like another asset from Jim's imgur. It's not bad, not sure how the team feels about it.]**
<img src="https://i.imgur.com/W9ahTXh.png">

As you can see, it's a tree-like data structure with the top (root) being the `document` object.

**^^ [tktk tktk This will need to change if the above asset becomes drastically different.]**

<details>	
<summary>❓ What JS data type would each of those nodes be?
</summary>
<hr>

**Nodes most certainly will be JS objects with properties used to get/set information and methods to manipulate the DOM.**

<hr>
</details>

**^^ [tktk tktk This will also need to change if the above asset becomes drastically different.]**

If we type `document` in DevTool's console, we'll see the HTML-centric representation of the document, however, we want to explore the JavaScript data structure that is the DOM.  We can do this by typing `dir(document)` in console and exploring the objects and properties of the DOM.

The DOM has an application programming interface ([API](https://en.wikipedia.org/wiki/Application_programming_interface)) that enables developers to make the UI dynamic by using JavaScript to:

-  Add/remove elements to/from the document
-  Change the content of elements
-  Change an element's styling
-  Listen for events, e.g., when an element is clicked
-  Animate elements


> **tktk tktk Below are the steps for the set up, it will just need to be formatted to match all of the other modules**


### Create the Project Files
1. Make sure you are in your root directory: `cd ~`
2. Make a `code` folder (*if you haven't yet*): `mkdir code`  
3. Move into your `code` folder/directory: `cd code`	
4. Create a new directory named `dom-practice`:  `mkdir dom-practice`
5. Move into the new directory: `cd dom-practice`
6. Create an `index.html` file:  `touch index.html`
7. Open the directory in VS Code: `code .`
8. Open `index.html` in the editor and use `! [tab]` to create the HTML boilerplate
9. Create a `js` directory and touch a `js/main.js` file
10. Add a `<script>` tag to include `main.js` in the `<head>`:

	```html
	<head>
	  ...
	  <title>DOM Practice</title>
	  <script defer src="js/main.js"></script>
	</head>
	```
	> The `defer` attribute ensures the DOM is ready before the script executes.
11. Finally, let's add an `<h1>` inside of the `<body>` as follows:

	```html
	...
	<body>
	  <h1 id="title" class="main-title">DOM Practice</h1>
	  
	</body>
	</html>
	```
