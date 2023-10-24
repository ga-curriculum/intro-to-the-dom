# ![Intro to the DOM - Setup](../assets/tktkhero-main-subhead.png)

Open your Terminal application and navigate to your `~/code/ga/lectures` directory:

```bash
cd ~/code/ga/lectures
```
Make a new directory called `dom-intro`, then enter this directory:

```bash
mkdir dom-intro
cd dom-intro
```

Create a directory called `js`:

```bash
mkdir js
```

Then, create an `index.html` file, as well as a `app.js` file inside the `js` directory. These files will hold your work for this lecture:

```bash
touch index.html ./js/app.js
```

With the files created, open the contents of the directory in VS Code:

```bash
code .
```

Open the `index.html` file and add HTML boilerplate by typing `!` and then hitting the `Tab` key. Then make use of the `app.js` file inside of the `js` directory by adding this line inside the `<head>` tag:

```html
<script defer src="./js/app.js"></script>
```

Finally, let's add an `<h1>` inside of the `<body>` as follows:

```html
	<h1 id="main-title" class="title">DOM Practice</h1>
```

Open the `index.html` file in your browser.
