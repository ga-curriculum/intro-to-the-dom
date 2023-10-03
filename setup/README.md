# Intro to HTML - Setup

![Hero image](../assets/tktkhero-main-subhead.png)

**Learning objective:** By the end of this lesson, students will be able to create a new directories and files for HTML and JS to practice DOM concepts, fundamentals, and manipulation.

********************************************************************************
********************************************************************************

Below are the steps for the set up, it will just need to be formatted to match
all of the other 

********************************************************************************
********************************************************************************


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
