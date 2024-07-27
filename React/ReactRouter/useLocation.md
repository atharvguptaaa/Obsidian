This hook returns the current [`location`](https://reactrouter.com/en/main/utils/location) object. This can be useful if you'd like to perform some side effect whenever the current location changes.

```js
import * as React from 'react';
import { useLocation } from 'react-router-dom';

function App() {
  let location = useLocation();

  React.useEffect(() => {
    // Google Analytics
    ga('send', 'pageview');
  }, [location]);

  return (
    // ...
  );
}
```

#### Properties

##### location.pathname
The path of the current URL.
##### location.hash
The hash of the current URL.
##### location.key
The unique key of this location.
##### location.search
The query string of the current URL.
##### location.state
The state value of the location created by <Link state> or navigate.

![[Screenshot 2024-07-25 155509.png]]