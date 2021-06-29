# Section 18 | Redux

### 225 - Different types of State

| Local | Cross-Component | App-Wide |
| ------ | ------ | ------- |
| State that belongs to a single component | State that affects multiple components | State that affects the app (most of the components) |
| Should be managed by `useState` or `useReducer` | Requires `props` chaining | Requires `props` chaining/ `useContext` can be of help |

### 226 - Why Redux?

* You can use both **Redux** & `Context` in the same app. 
* You can use **Redux** as the App-Wide state manager and `Context` as the Cross-Component state manager.

**React Context** - Potential Disadvantages

* For small and medium project `Context` is alright.
* For bigger apps, using `Context` can be complex.
* You can end up deeply nested `jsx context provider`.
* For the changes that are more frequent, `Context` has performance issues w/ them.


### 227 - How Redux works?

* With Redux we get one Central Data(State) Store. Always.
* But it's not unmaintainable. We can split actions and use the Central store.
* The components that are subscribed to the store, get access of the store actions and hence update the state.

> Component never manipulate the store's data

* We use Reducer Function for mutating/ manipulating store data.
* In general, Reducer functions take an input and returns a different output.

> First the subscribed component triggers an action, then the action is forwarded to the Reducer Function, then the Reducer updates store data and that becomes visible in the subscribed component.


### 228 - core concepts exercise

* The Reducer Fn takes two params, 
	- the old/ existing state
	- dispatched action
* Then this Fn must return a New State Object.
* Therefore, the Fn should be a pure Fn(Same input leads to same output) and it shouldn't have any side-effects (no localStorage & http usages).
* The `store` variable that stores the redux createStore, get `.getState()` as a method. 
* It will update when the `store` changes.
* To make the redux aware of the Subscriber Fn, we use `.subscribe()` method from `store`.
* Use `.dispatch()` for dispatching an action. 
* It takes an obj. The obj has a `type` property and an optional payload.


### 233 - Using redux store data in components

* `useSelector` of `react-redux` is a custom hook.
* It helps us to select a part of the state that is managed by the store.
* It is the alternative of `connect` used in the class-based component.
* This fn gives us a part of our state data from the store.

```js
  const counter = useSelector(state => state.counter);
```

* Here we only extracted the counter state from the store state.
* It updates the counter automatically when the store updates or subscribe automatically.

### 234 - dispatching actions from component

* For dispatching, use `useDispatch`.
* Then pass types to the dispatch on trigger to send request updating on the store.


### 236 - attatching payloads

* We can send payload like a value or an obj.
* For value only, we need to access it in the reducer as a property of `action` obj.

### 237 - multiple state properties

* 






















