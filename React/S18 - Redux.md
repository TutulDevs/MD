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

* 
