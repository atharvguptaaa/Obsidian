#javascript 
Promises in JavaScript are <font color="#2DC26B">objects</font> that represent the eventual completion (or failure) of an <font color="#2DC26B">asynchronous</font> operation and its resulting value. They are used to handle asynchronous operations like API calls, file reading, or timers, allowing you to write cleaner code without getting into the complexities of callbacks or nested callbacks, which can lead to <font color="#2DC26B">callback hell</font>.

The JavaScript Promise object precisely holds the following:

1. **State:**
    
    - A Promise can be in one of three states:
        - **Pending**: The Promise has been initialized but hasn’t completed its operation yet.
        - **Fulfilled**: The operation completed successfully, and the Promise holds the resulting value.
        - **Rejected**: The operation failed, and the Promise contains the error or reason for failure.
2. **Result:**
    
    - The outcome of a Promise depends on its state:
        - If fulfilled, the result is the value with which it was resolved.
        - If rejected, the result is the reason or error explaining the failure.
3. **Handlers:**
    
    - Handlers are functions attached to a Promise to handle its resolution or rejection.
    - Key methods for handling Promises:
        - `.then()`: Handles successful resolution (fulfillment) with one or two callback functions.
        - `.catch()`: Specifies a callback for handling rejection.
        - `.finally()`: Executes a callback when the Promise settles (regardless of outcome).

```js
let promise = new Promise(function(resolve, reject) {
    setTimeout(() => {
        // Simulate a task that takes time, like an API call
        const success = true; // Change this to false to simulate failure
        if (success) {
            resolve("Task completed successfully!");
        } else {
            reject("There was an error!");
        }
    }, 1000);
});

promise.then(result => {
    console.log(result); // Logs "Task completed successfully!" if successful
}).catch(error => {
    console.error(error); // Logs "There was an error!" if there is a failure
}).finally(() => {
    console.log("Operation attempted");
});
```

[[async and await]] are extensions of promises that make asynchronous code look and behave a little more like synchronous code. 