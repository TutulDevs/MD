# Section 15 | Custom Hooks


### 185 - What is it?

* Custom Hooks outsource stateful logic into re-usable functions.
* Unlike other regular functions, custom hooks can use the other hooks from React and React state.


### 186 -  Creating

* When we call two or more similar component functions, Hooks can refactor the code and make it lean.
* While creating the function, it's mandatory to use the prefix `use` before the hook/ function name.
* Then we can put the logic into the function w/o returning anything yet.

### 187 - Using

* We can return anything in the custom hook function. It can be array, string, number, object or maybe the state in that function.
* Now in the main function, where we import the custom hook, we can store the returned value in a variable and use it for our app.

### 188 - Configuring

* We can set a argument and output result based on the condition of the argument.


### 189 - 193 | More Realistic Example

* In these lectures we saw how to create an actual custom hook and making it re-usable in any situation.
* We should be careful on the `Object` mutability and carefully use `useCallback`.
* For the dependency we can use arguments on an inside function because function arguments don't have any side-effects.


















