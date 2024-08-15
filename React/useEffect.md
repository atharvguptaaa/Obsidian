[Common mistakes in UseEffect](https://youtu.be/QQYeipc_cik)

- 🏃 useEffect runs after rendering and can be used to perform various tasks.
- 🏃 Dependencies in useEffect determine when the effect should run.
- 😨 Care should be taken when using non-primitive dependencies(objects and arrays), as React compares their references instead of their content.
- ❓ useMemo can be used to memoize values in the state and optimize performance.
- 🔁 Updating state using an updating function instead of the state variable itself can prevent infinite loops in useEffect.
- ❓ <font color="#9bbb59">Clean-up functions</font> in useEffect are important to prevent memory leaks and cancel ongoing tasks.
- 🆘 React Strict Mode helps identify potential issues in the useEffect lifecycle.

##### Cleanup function in UseEffect:
It runs :
- before the component unmounts or
- before the effect runs again. 
It's used to clean up things set up by the side effect to prevent memory leaks or other issues. For example, if you set up a timer, the cleanup function can clear the timer.

```js
//SYNTAX :-
useEffect(() => {
  // Your side effect code here
  return () => {
    // Cleanup code here
  };
}, [dependencies]);
```

```js
//APPLICATION :-
function App() {
const [number, setNumber] = useState(0);
useEffect ( ( ) => {
console.log("effect")
const interval = setInterval(() => {
setNumber (prev=>prev+1);
}, 1000);
return ()=>{
clearInterval(interval)    //cleanup function
}
}, []);

return <div>{number}asd </div>;
}
```
