# Section 19 | Redux Advance

### 249 - Redux & Side Effects

* Reducers must be pure, side-effect free, synchronous functions.
* It'll return the same obj that it received.

**Where should side-effects & async task be done?**

1. Inside the components via `useEffect` or
2. Inside the **action creators**. We'll ditch the Redux given action creators & make ours own.

### 253 - Backend vs Frontend

* Usually on Backend, there will be logic to transform and storing data. 
* Then on the frontend, it's less work.
* On Firebase's RTDB, you don't get the options, unless use **Functions** option on FB.
* There you'll have to work on fronend for storing & fetching.

### 254 - Where to put the logic?

* We can put it in the component.
* But we'll have to write the same logic everytime when that action triggers on each component.
* We could make the redux reducer kind of idle because it won't do much if we work on the component.

* **IMPORTANT** : if the code is synchronous, side-effect free, 
	- prefer reducers
	- avoid action creators or components
* If the code has async task w/ side-effect: 
	- prefer action creators or components
	- never use reducers

### 255 - using `useEffect` w/ redux

* We can use `useEffect` to update the async task, like updating the FB.
* We can use `method: 'PUT'` on fetch to POST data but w/o creating a new item. PUT will update the existing data.
* In this way, first it updates the frontend and then the backend.

### 256 - problem of `useEffect`

* `useEffect` will execute on the initial render which may have an empty state.
* Then it'll send the empty state to FB. 
* It's gonna be solved in the next lectures.


### 258 - using action creator thunk

* **Thunk** is a function that delays an action until later, until something is finished.
* An action creator fn that does NOT return the action itself but another function which eventually returns the action.
* We can use a function that returns another function as an action. Redux Toolkit understands it.


### 261 - fetching data 

* When fetching an array from a db, make sure if it gets undefined. In that cases, use the logical OR `||` to add an empty array. 
* This will help to not throw an error if you use any array method anywhere on the code.


