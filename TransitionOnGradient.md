# Fix CSS transition on gradient background

Recently I discovered that CSS gradient background doesn't support the `transition` property. But there's a way to fix that.

In this tutorial we're going to solve that problem. Here's the [final result](https://all-js.netlify.app/34-darkMode/fixgradtrans). 

> This tutorial's code is based on my previous blog on making [dark mode](https://tutuldevs.hashnode.dev/darkmode). Read that article or see the [source code](https://github.com/TutulDevs/All-JavaScript/tree/master/34-darkMode).

In this project we'll change the CSS gradient background of a selected element (in our case the `body`) by clicking on a button. If you don't want the click function, no problem. You can change the gradient on hover too. The recipe is almost the same.

So let's start.

## Method

Out element will have a gradient background and transition time. In the `::before`  pseudo selector,  we'll set another gradient background but it'll be invisible. On click or on hover the background of the pseudo element will be visible.

## Step 1 

Set a gradient background(of any type), a preferable transition, position it relatively and stact it on top it's children elements.

```css

body {
    width: 100%;
    height: 100vh;
    font-family: 'Montserrat', sans-serif;
    color: #333333;    
    
    transition: all 0.5s linear;
    background: repeating-linear-gradient(-55deg, #fff 5%, #ddd 50%);
    position: relative;
    z-index: 1;
}

```

## Step 2 

Now give the `::before` pseudo selector of the element same height, width, transition and another gradient background. Later stack it below the parent element, delay the transition(optional) and make it invisible. 


```css

body::before {
    content: ' ';
    position: absolute;
    width: inherit;
    height: inherit;
    transition: inherit;
    
    background: repeating-linear-gradient(-55deg, #343A40 5%, #202C39 50%);
    z-index: -1;
    opacity: 0;
    transition-delay: 0.3s;
}

```

## Step 3 

Now on click event, we'll make the `::before` element visible. If you want the change on hover, use `element:hover::before`.

```css

.dark::before{
    opacity: 1;    
}

```

Well done. Now you can see that the background is changing smoothly. Here's the [source code](https://github.com/TutulDevs/All-JavaScript/blob/master/34-darkMode/fixGradTrans.html).



---

Thanks for reading. Feedback will be appreciated. Let's connect on [Twitter](https://twitter.com/TutulDevs).

Cover image is brought from [gradienta.io](https://gradienta.io).
