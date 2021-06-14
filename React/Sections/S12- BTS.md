# Section 12 | React BTS

We are going to learn three main things.

1. How React works Behind The Scenes?
2. Understanding the Virtual DOM & DOM Updates.
3. Understanding State & State Updates.

## 151 

* React creates a virtual DOM for comparing with the Real DOM. 
* When a state updates, React compares the two DOMs and finds out the dirrefences. (*Virtual DOM Diffing*)
* Then it renders only the changed part of the DOM. This way it takes less memory and perform better. 

> Re-evaluating Component !== Re-Rendering Component


## 154 - `React.memo()`

* If nothing changed, then `memo()` will help us to not re-execute the embraced component.
* Wrapping a component with `memo()` does two things: 

    1. Stores the previous state's value
    2. Compares with the new value.
    
* That's why `memo()` can make a performance issues. Because it does tasks and takes time.
* It can be helpful if you've a big component tree to remove unnecessary re-execution.
* Everytime the `App` function re-renders, all the arrays and objects including the functions are hoisted(kinda) in React's stack. That's why `memo()` can't differentiate the changes by `reference values`, only `primitive values`.
* So, is `memo()` useless for the components that receive array/ object/ function? **NO**


## 155 - `useCallback`

* We can use `useCallback` to tweak the objects a little bit to work on `memo()`.
* It tells React that we want to save an `Object` and it shouldn't be recreated on every execution.
* It'll save the `Object` somewhere in React's internal storage and use that on every function call or execution.
* To use it first import it and then wrap the function with it.
* It expect a second param that may cause the change.(like the `useEffect`)

```js
  const togglePara = useCallback( () => setShow( prev => !prev), [] );
```












