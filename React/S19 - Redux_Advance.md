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



















