In JavaScript, `const` variables cannot be reassigned after their initial assignment, which means you cannot change the reference they hold once they've been defined. However, if a `const` variable holds an object or an array, you can still modify the contents of the object or array without changing the reference itself. Here are a few scenarios to explain this behavior:

### Scenario 1: Reassigning a `const` primitive variable

```js
const myNumber = 10; myNumber = 20;  // This will throw a TypeError
```

### Scenario 2: Modifying a `const` array

```js
const myArray = [1, 2, 3]; myArray.push(4); // This is allowed, myArray is now [1, 2, 3, 4]
```

### Scenario 3: Modifying a `const` object

```js
const myObject = { key: 'value' }; myObject.key = 'newValue';  // This is allowed, myObject is now { key: 'newValue' }
```


In scenarios 2 and 3, <font color="#9bbb59">the `const` variable is not being reassigned; instead, the contents of the object or array are being modified. The reference to the array or object remains the same, which is why no `TypeError` is thrown.In JavaScript, </font>`const` variables cannot be reassigned after their initial assignment, which means you cannot change the reference they hold once they've been defined. However, if a `const` variable holds an object or an array, you can still modify the contents of the object or array without changing the reference itself. Here are a few scenarios to explain this behavior:

