# Section 10 | Side Effects, Reducers, Context API 


### 120 - 125 | Context API

* For bigger apps, lifting states and fetching from `props` can be lots of work and many components may not use the `props` but access it to lift that to the needed component.
* There comes the React behind the scene's storage, `Context API`. It can keep the state's value and use it only in the specific component where it needed.

#### Using Context

* Create file under a store folder for using the `Context API`.
* In that file, use React to create a context by `React.createContext` and inside that pass an object with initial key-value pair.
* Keep the context inside a variable and export it since we're going to use it.
* Then go to the parent component where it needs and wrap the components with `<NamedContext.Provider>` and give it a value prop to update or interact with the state.

```js
    <AuthContext.Provider value={{isLoggedIn,}}>
     	// Some components
    </AuthContext.Provider>
```

* Now, to consume/ use it, we have two ways.

**Way 1**

* One is to wrap the child component that need to use the context with `<NamedContext.Consumer>` and inside of this wrapper use a function to return the context object. 

```js
    <AuthContext.Consumer>
      {(ctx) => {
        return (
          <nav className={classes.nav}>
            <ul>
              {ctx.isLoggedIn && (
                <li>
                  <button onClick={props.onLogout}>Logout</button>
                </li>
              )}
            </ul>
          </nav>
        );
      }}
    </AuthContext.Consumer>
```

* Use the `ctx` param instead of `props`.

**Way 2**

* We can import `useContext` from React and pass the `NamedContext` inside it and store it's value in a variable.

```js
  const ctx = useContext(AuthContext);
```

* Then just replace `props` with the variable name. 

* Besides objects, we can add **function** in the value of `Context.Provider`. So that state changes through the function will be triggered.

* We can create a function inside the context to pass all the value and the `props.children` to make the code leaner. This way all the data stored in the central `<App />` component and we can use it whenever or whereever we need it.


**Context Limitations** 

* Context is not good for state changes that happen very frequently, like multiple in a second. 
* Context shouldn't replace all component communication and `props`.
* For configuration still `props` is a better option.





