## question
how to put input of one component to display in another react component?
## answer -
To pass the input from one React component and display it in another, you can use a combination of state lifting and props. Here's a step-by-step guide on how to achieve this:
### Step 1: Create a Parent Component
This component will hold the state that stores the input value. It will also render both the input component and the display component.

### Step 2: Create an Input Component
This component will accept a function via props that it calls to update the state in the parent component whenever the input changes.

### Step 3: Create a Display Component
This component will accept the input value via props and display it.

Here’s an example to illustrate this:

#### ParentComponent.jsx
```jsx
import React, { useState } from 'react';
import InputComponent from './InputComponent';
import DisplayComponent from './DisplayComponent';

function ParentComponent() {
  const [inputValue, setInputValue] = useState("");

  const handleInputChange = (value) => {
    setInputValue(value);
  };

  return (
    <div>
      <InputComponent onInputChange={handleInputChange} />
      <DisplayComponent inputValue={inputValue} />
    </div>
  );
}

export default ParentComponent;
```

#### InputComponent.jsx
```jsx
import React from 'react';

function InputComponent({ onInputChange }) {
  return (
    <input
      type="text"
      onChange={(e) => onInputChange(e.target.value)}
      placeholder="Type here..."
    />
  );
}

export default InputComponent;
```

#### DisplayComponent.jsx
```jsx
import React from 'react';

function DisplayComponent({ inputValue }) {
  return <p>Current Input: {inputValue}</p>;
}

export default DisplayComponent;
```

### Explanation:
- **ParentComponent**: Manages the state and passes the handler and state to child components.
- **InputComponent**: Takes user input and notifies the parent component of changes via a function passed as a prop.
- **DisplayComponent**: Receives the input value via props and displays it.

This setup ensures that the input in one component is effectively passed and displayed in another, maintaining a clear separation of concerns and leveraging React's unidirectional data flow.