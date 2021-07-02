# Section 20 | Route

### 270 - dynamic routh path w/ param

* For dynamic route path, on the path use a `colon (:)` after the path and an identifier on the right.

```js
	<Route path='/product-detail/:productId' component={ProductDetail} />
```

* The url will look like this, `url.com/product-detail/p1`

### 271 - extracting route param

* We can get the param by a hook by route team, the `useParams` hook.
* It'll contain all the identifier from the url and store it in a obj.

### 272 - using `Switch` & `exact`

* In general, routes are rendered on a single page, one under another.
* But if we wrap the routes in `Switch` from react-router, only one path or component will be rendered.
* In `Switch`, react-router will get the first matching path and stops rendering there. It doesn't go for exact or elaborated path.
* One way to solve this issue is by place the elaborated path on top of the less elaborated path.
*  Another way is to add `exact` on the less elaborated route. It tells to render the component on exactly the same path.



### 273 - nested route

* Nested route simply means that you can use <Route path=''  /> in any component.
* The nested route will be rendered when the parent route is rendered.

### 274 - Redirect

* Redirect redirects to a route on an action or for showing the default page.











