#  Dark Mode with only one line of JavaScript 😎

Dark mode is a necessary feature in a modern website. It not only makes the site look cool, but gives the audience an option to feel comfortable too.

In this tutorial we are going to build a simple web page with the option to switch between dark and light color theme. It'll require very basic knowledge of JavaScript and DOM. If you don't know JavaScript, don't fret. It's only one line of code and I'll clarify how that works. Take a look at the [end result](https://all-js.netlify.app/34-darkMode).

>
>  This project is a part of my JavaScript [mega project](https://all-js.netlify.app).

Let's start building ✌️

## HTML

In our design we'll have a simple layout. It'll contain a `header`, `article` and `footer`. The `header` will contain a logo and a button for toggling modes. The `article` will have a headline and a link. Let's write the code inside the body.


```html

<header>
    <h2>
        Logo
    </h2>
    <button id="toggle">
        🔅
    </button>
</header>

<article>
    <h1>
        Toggle dark mode with one line of JavaScript 😎
    </h1>
    <a href="#">
        Tutorial
    </a>
</article>

<footer>
    <p>
        Copyright @ 2020
    </p>
</footer>
```

Now set a function to  the button, that will run/ called when it is clicked. We'll write the JavaScript function later. Name the function `mode`.

```html
<button id="toggle" onclick="mode()">
    🔅
</button>
```

## CSS

First set up some global styling to our page. I've imported a font from [Google Fonts](www.fonts.google.com), set the `color`, `background-color` and `transition` for the `body`.

```css

@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300;500&display=swap');

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    width: 100%;
    height: 100vh;
    font-family: 'Montserrat', sans-serif;
    background: #eeeeee;
    color: #333333;
    transition: all 0.5s ease-in;
}

```

For the layout we'll separate those three parts with `vh` unit values.

```css

header {
    height: 25vh;
}

article {
    height: 60vh;
}

footer {
    height: 15vh;
}

```

Now let's add the styling to the skeleton. For the `header`, we'll place the child elements on oppsite direction of each other. For the `article` and `footer`, we'll place the child elements in the center of their parent elements.

```css

header {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

article,
footer {
    display: grid;
    gap: 15px;
    justify-items: center;
    align-content: center;
    text-align: center;
}

```
If you notice you'll see that the child elements of the `header` are like touching the walls and the button's font-size is small. Let's fix this. Also make the link a bit nicer.

```css

body > * {
    padding: 0 15px;
}

a {
    text-decoration: none;
    font-size: 20px;
    color: #ffffff;
    padding: 10px 25px;
    background: teal;
    border-radius: 25px;
    transition: all 0.5s ease-in;
}

#toggle {
    cursor: pointer
    font-size: 25px;
}

```

Now let's create a CSS class selector and add our dark color scheme inside that class. Later via JavaScript, we'll add that class selector to the `body` and toggle between modes. So the `color` and the `background-color` of the `body` will change.

```css

.dark {
    color: #ffffff;
    background: #333333;
}
.dark a {
    background: #37d796;
}

```

Our basic CSS is done here.

## JavaScript

Since we added `onclick` on the button, we'll just create the function here. It's only one line so I'll add it inside my HTML page.

```js

<script type="text/javascript" charset="utf-8">
    const mode = () => document.body.classList.toggle('dark');
</script>

```

I've used `arrow function` in my example for one line's sake, but any regular function will work the same. Like this:

```js

function mode(){
    document.body.classList.toggle('dark');
}

```

Let me explain the code to you. In the HTML we set a click event. We literally said that if the button is clicked, run the `mode` function.
In our JavaScript we created the `mode` function. Inside the function we located the `body` element by `document.body`. Then we used the `classList API`. It'll return a class to the `body` element.
After that, we used  `toggle('dark')`.
`toggle` will toggle/ switch the class in the `body`. More clearly, if the `body` doesn't have the class, it'll add that class. If the element has the class, it'll remove that class.

## Changing the toggle  icon

There are several way to change the icon but we're going to use the simplest way. We'll use the `::before` pseudo selector to achieve that. So our button won't have an icon of it's own but it's pseudo selector's. On toggle we'll change that by using any emoji inside the `content: ' '`.

Edit HTML
```html

<button id="toggle" onclick="mode()">
    <!-- 🔅 changed in css  -->
</button>

```

And CSS
```css

#toggle {
    cursor: pointer;
    font-size: 25px;
    width: 50px;
    height: 50px;
    border: 0;
    background: transparent;
    position: relative;
}

#toggle::before {
    content: '🔅';
}

.dark #toggle::before {
    content: '🔆';
}

```

Congrats! You've made it. let me know your thoughts. If you think you need the source code, here's the [link](https://github.com/TutulDevs/All-JavaScript/tree/master/34-darkMode).

## Considerations

1. The button has accessibility issues since there's no text. Try to use `aria-label` or add `.sr-only`.

2. Emojis look different based on the system or app. So try to use alternative, like SVG icons.

3. `transition` property doesn't work on CSS gradient backgrounds.  But you can make that work by using a simple technique. That's going to be my next blog 🤞.

----

Thanks for reading this far. I regularly update my learning in [Twitter](https://twitter.com/TutulDevs). Feel free to connect.


Cover image is brought from [Unsplash](https://unsplash.com).
