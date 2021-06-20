# Section 16 | Forms

### 197 - Whats so complex about Forms?

* Forms and inputs can assume different states.
* When to validate?

| on submit | on losing focus | on every keystroke |
| ---- | ---- | ---- |
| Allows the user to enter a valid value before warning | Allows the user enter a valid value before warning | Warns user before s/he had a chance of entering valid values |
| Avoid unnecessary warnings but maybe present feedback "too late" | Very useful for untouched forms | If applied only on invalid inputs, has the potential of providing more direct feedback |


### When to use what to get the value from an input?

* If you want the value after submitting the form or only once, `useRef` is better. `onChange` and state update is a bit overkill then.
* If you need the value on every keystroke to validate(maybe), then state is better.
* If you want to reset the form, state can be of help.


```js
	//Don't use any of these to reset
	
	e.target.reset();
	nameRef.current.value = '' ;
	
	// they deal w/ the DOM itselt. We should let React do that.  
```


### 199 - Validating

* Validating on the client side is good for practicing or for UX, but you should always validate on the server. Because an user can change the validation from the source and that's not what we want.


### 201 - Handling with 'touched'

* Using touched to handle the form submission is a bit more better and convenient. 

### 204 - Managing the overall form validity

* The most efficient way to find the overall validity is to set a variable, initially as `false`. 
* Then check all the inputs if they aren't empty. If all are filled, set the variable as `true`.

```js
  // IF name isn't empty, form is valid, otherwise not
  
  let formIsValid = false;
  if (nameIsValid) formIsValid = true;
```


### 205 - Custom Input Hook

* Due to the multiple input checks and writing almost the same code again and again, we can create a custom hook to automate the task.
* Our hook will get a function as a param. The function will get the entered value and do the validity check.
* Then we'll declare states, check validity, update states and return an object where we'll send all the data we'll need while using the hook.
* While using, we store the hook in an destructured object with alias. Then on the right side, inside the `()`, we'll pass the validity checking method. 
* We'll create each variable to use the custom hook for multiple input elements.


### 210 - `useReducer` 

* We can try using `useReducer()` in our input hook if there's multiple data needed to be changed. 
* We can try third-party library, like, Formik. 

