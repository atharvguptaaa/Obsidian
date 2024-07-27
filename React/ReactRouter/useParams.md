#react-router-dom 

The `useParams` hook returns an object of key/value pairs of the dynamic params from the current URL that were matched by the `<Route path>`. Child routes inherit all params from their parent routes.

```js
//  App.js

import React from "react";

import {
	BrowserRouter as Router,
	Switch,
	Route,
	useParams,
} from "react-router-dom";

function BlogPost() {
	let { id } = useParams();
	return (
		<div style={{ fontSize: "50px" }}>
			Now showing post {id}
		</div>
	);
}

function Home() {
	return <h3>home page </h3>;
}

function App() {
	return (
		<Router>
			<Switch>
				<Route path="/page/:id">
					<BlogPost />
				</Route>
				<Route path="/">
					<Home />
				</Route>
			</Switch>
		</Router>
	);
}

export default App;

```

![[zz1 1.png]]


2nd example
<font color="#9bbb59">console.log(useParams())</font>

![[Pasted image 20240725163047.png]]