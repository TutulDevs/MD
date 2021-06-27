# Section 10 | Side Effects, Reducers, Context API 


### 115 - 119 | useReducer

* `useReducer` helps to manage multiple states and their updates.
* When you update a state which is dependent on another state, it's better to merge those states into one state.
* It can be done w/o `useReducer` too, but it can make code difficult to manage.
* We can use `useReducer` by destructuring two variable from `useReducer` and then pass a reducer function and an initial state object.

```js
  const [emailState, dispatchEmail] = useReducer(emailReducer, {
    value: "",
    isValid: null,
  });
```
* We can keep the reducer function outside of out main exporting function to make it lean. 
* That function will take two params, a state and an action. 
* This function will return a state object based on the condition and the action type.
* Later we can dispatch the dispatching function with a type and a payload which will update the state's value in the reducer function.

```js
  const emailChangeHandler = (event) => {
    dispatchEmail({
      type: "USER_EMAIL",
      val: event.target.value,
    });
  };
```

* We can use the value of the first variable from the `useReducer` in the `useEffect` to handle side effects.

* In the `useEffect` dependency, we should use the exact property from the array. Otherwise the effects will be running for any change on the object. We should be very careful whether we need the effect on every property of the object or not.

| **useState**  | **useReducer**  |   
|---|---|
| Main state management tool  | Great if you need more **power**, like object as state  |
| Great for independent piece of data  | Should be considered if you have related data/state  |
| Great if state updates are easy & in less places  | If you have complex state updates  |



