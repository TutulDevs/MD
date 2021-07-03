# Section 20 | Route Project

### 281 - 404 page

* To add a 404 page, use the path `*`.
* Make sure to keep this route on the bottom of all the other routes.

```js
  <Route path='*' component={NotFoundPage} />
```

### 282 - Pragmatic (Imperative) Navigation

* By using `useHistory` hook, we can use different history method to redirect to a route on triggering an action.

### 283 - using 'Prompt' to prevent unwanted route transition

* You can display a prompt via router.
* It will take two values.
* `when` only takes `boolean` value. IF true show prompt ELSE don't show.
* `message` takes a function with a param which gives the location. But it's to show the message which is a `string`.

```js
	<Prompt
		when={isEntering}
		message={(location) =>
			"Do you really want to leave the page?\nAll your entered data will be 		lost."}
		    />
```




















