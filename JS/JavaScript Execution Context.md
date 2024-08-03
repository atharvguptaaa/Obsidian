There are two kinds of Execution Context in JavaScript:

- Global Execution Context (GEC)
- Function Execution Context (FEC)
### **Global Execution Context (GEC)**

Whenever the JavaScript engine receives a script file, it first creates a default Execution Context known as the ****`Global Execution Context (GEC)`****.

The GEC is the base/default Execution Context where all JavaScript code that is ****not inside of a function**** gets executed.

> For every JavaScript file, there can only be one GEC.

### **Function Execution Context (FEC)**

Whenever a function is called, the JavaScript engine creates a different type of Execution Context known as a Function Execution Context (FEC) within the GEC to evaluate and execute the code within that function.

Since every function call gets its own FEC, there can be more than one FEC in the run-time of a script.

## How are Execution Contexts Created?

The creation of an Execution Context (GEC or FEC) happens in two phases:

1. Creation Phase
2. Execution Phase

Hitesh video: https://youtu.be/ByhtOgF6uYM?si=V4wIUAQmJefk6Xrj

![[Pasted image 20240802153858.png]]