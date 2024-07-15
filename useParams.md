#react-router-dom 

useParams Hook helps to access the parameters of the current route to manage the dynamic routes in the URL

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

![[Pasted image 20240716005636.png]]