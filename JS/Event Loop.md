### How the Event Loop Works

1. **Initialization**: The script starts executing, and synchronous code is pushed to the call stack and executed immediately.
2. **Event Queue:** When asynchronous events occur, such as user interactions (e.g., click events, keyboard input), HTTP responses, timers, or other asynchronous operations, they are placed into an event queue.
3. **Call Stack: —** The call stack is a data structure that keeps track of the currently executing code. It maintains a record of function calls and their respective contexts (local variables, parameters).
4. **Event Loop: —** The event loop continuously monitors the call stack and the event queue. When the call stack is empty (i.e., no code is executing), the event loop takes the first event from the event queue and pushes its corresponding callback function onto the call stack. This process is known as “**popping an event off the queue.**”
5. **Execution of Callbacks: —** The callback function from the event queue is executed. If the callback itself contains asynchronous code (e.g., an asynchronous API call, a **setTimeout**), it’s scheduled to run later, and the event loop continues to process other events.
6. **Non-blocking Behavior: —** The event loop ensures that asynchronous operations do not block the main thread, allowing other events to be processed concurrently.
7. **Completion: -** The event loop keeps running as long as there are events in the queue or pending callbacks. When the queue is empty, the event loop will eventually terminate.

![[Pasted image 20240802182303.png]]

