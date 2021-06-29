# Section 18 | Redux w/ Toolkit

### 239 - Intro

* Redux problems
	- State immutability
	- Too much reducers for a big project
	- Unexpected typos

* Redux Toolkit helps with these problems.

### 240 - Adding State Slices

* `createSlice` from redux-toolkit takes an obj which shortens the hassle of redux.
* It needs the name of the state slice, an initial state and a reducers obj.
* Inside reducers obj, we can add multiple case or if check type of function but in an efficient way.
* In reudecers, we can update an obj by mutating.
* We can use actions in a function if needed. Otherwise, state alone is ok.

### 241 - Connecting Redux Toolkit state

* Store the slice of state in a variable.
* For storing the slice, use `configureStore`.
* This obj will have a `reducer` key and the slice will be the state slice
* If you've multiple slices, use an obj with a key to store the slice.


```js
  // IF it's one slice
  const store = configureStore({
    reducer: counterSlice.reducer,
  });

  // IF it's multiple slices
  const store = configureStore({
    reducer: { 
      counter: counterSlice.reducer, 
      random: randomSlice.reducer 
    },
  });
```

### 242 - Migrating eveything to the Redux Toolkit

* The stored `counterSlice` has a `.actions` method added by Redux Toolkit which gives access to the action.type and action.payload.
* Store that actions and export it.
* In the main component, import the actions variable.
* It'll have all the methods of reducers.
* Call it like an invoking fn with `()`

```js 
	// w/o payload
	dispatch(counterActions.increment())
	
	// w/ payload is one
	dispatch(counterActions.increment(5))
	
	// w/ payload is multiple
	dispatch(counterActions.increment({ amount: 5} ))
```


### 243 - Working with multiple slices

* On multiple states merged in the `configureStore`, use the token/ key name while using `useSelector` function.

```js
  const auth = useSelector((state) => state.auth.isAuth);
```

### 245 - Splitting code

* Make seperate file for each `createSlice`.
* Export the variable of the actions from that file.
* Export default the slice variable with `.reducer`.


