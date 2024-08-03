### UseCallback
**useCallback** is a hook that returns a memoized callback. A callback is a function that is passed as an argument to another function. In the context of React, a callback is often used as an event handler or to pass data between components. 

The **useCallback** hook takes two arguments: a function and a dependency array. It will return a memoized version of the function that only changes if one of the dependencies has changed.

Here's an example of how you might use the **useCallback** hook:

```js
import { useCallback } from 'react';

function ParentComponent() {
  const [count, setCount] = useState(0);
// this function will only be recreated if count changes
  const handleClick = useCallback(() => {
    setCount(count + 1);
  }, [count]);

  return (
    <ChildComponent onClick={handleClick} />
  );
}

function ChildComponent({ onClick }) {
  return (
    <button onClick={onClick}>Click me</button>
  );
}

```

The **useCallback** hook ensures that the handleClick function is only re-created if the count prop changes. This can be useful if the ParentComponent is re-rendered frequently, as it can help to prevent the function from being unnecessarily re-created.

### UseMemo

**useMemo** is a hook that returns a memoized value. It takes two arguments: a function that returns a value and a dependency array. It will call the function and return its result only if one of the dependencies has changed.

Here's an example of how you might use the **useMemo** hook:
```js
import { useMemo } from 'react';

function MyComponent(props) {
  const { data } = props;

  const processedData = useMemo(() => {
    // do some expensive processing with data
    
    return processedData;
  }, [data]);

  return <div>{processedData}</div>;
}

```

 The **useMemo** hook ensures that the processedData value is only re-computed if the data prop changes. This can be useful if the processing is time-consuming and you don't want it to be re-done unnecessarily.

### Key Differences:
- With `useCallback` you can define a function that has referential equality between renders.
- You can use `useMemo` to calculate a value that has referential equality between renders.