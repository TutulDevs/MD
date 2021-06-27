# Section 10 | Side Effects, Reducers, Context API 

### 109 - 114 | Side Effect/ useEffect

* The main jobs of React are a) Rendering UI, b) Detect user's interaction, c) update the UI based on the interaction if needed.
* Side effect is anything that happens beyond React's area. 


* The `useEffect` is called with two arguments. 
* The first one is a function that should be executed after every component evaluation if the specified dependencies changed.
* The specified dependencies are the second argument.
* An array full of dependencies & whenever such dependency changes that first function will run. 

```js
 useEffect( () => {...}, [ dependencies ] );
```

* Without any  dependencies the function will run when the component loads for the first time.
* Add the things you're using to execute the function for as dependencies.
* If any of the dependencies change, run the function.
* If none of the dependencies change, don't run the function.
* Only add the states that is going to change.

** What to add/ not to add as dependencies**

* No need to add state updating funtion name
* No need to add browser APIs, like, `fetch()`, `localStorage` etc.
* No need to add outside's variables or functions.
* So long story short: You must add all "things" you use in your effect function **if those "things" could change because your component (or some parent component) re-rendered**. That's why variables or state defined in component functions, props or functions defined in component functions have to be added as dependencies!

**Debouncing**

* We don't need to run the function on every keystrokes. We may just need to check it after a while. 
* This is called debouncing. 
* In `useEffect`, you can `return` anything, even a function. 
* The returning arrow function is also called as a **clean-up** function.
* This will work as a clean-up function before `useEffect` execute the function the next time.
* It doesn't run when the component is rendered for the first time.

**Summary From Sumit Saha**

* Without `[]`, the `useEffect` will run on any state update.
* With `[]`, the `useEffect` will run only for the first render.
* With dependency inside of `[]`, the `useEffect` will run on that specific state update.
* You can return a function to clear the first function to stop when it's unmounted.(componentWillUnmount)
* So `useEffect` can alone do all the tasks that all the LifeCycle Methods did previously, with more code.

