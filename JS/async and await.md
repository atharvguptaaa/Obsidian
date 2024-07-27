#javascript 
## async
##### Usage: 
You place async before a function declaration to indicate that the function is asynchronous. This means the function can perform tasks that might take some time to complete, like<font color="#2DC26B"> fetching</font> data from a server,<font color="#2DC26B"> without blocking</font> (stopping) the rest of your code from running.
##### Returns: 
 An async function always returns a <font color="#2DC26B">promise</font>. A promise is an object that represents a value which may not be available yet but will be resolved at some point in the future.
## await
##### Usage: 
You use await inside an async function to pause the execution of the function until a promise is resolved or rejected (i.e., the asynchronous operation completes). This lets you <font color="#2DC26B">write asynchronous code almost as  if it were synchronous</font> (sequential), making it easier to read and understand.

##### Effect: 
When you await a promise, the function execution pauses at that point and resumes once the <font color="#2DC26B">promise settles</font> (either fulfilled or rejected). The value returned by the await expression is the resolved value of the promise.  


```js
async function getUserData(userId) {
    console.log("Fetching user data...");
    const response = await fetch(https://api.example.com/users/${userId});
    const data = await response.json(); // Convert the response to JSON
    return data; // This will be the resolved value of the promise returned by the async function
}

getUserData(1).then(data => console.log(data)).catch(error => console.error("Error:", error));
```

