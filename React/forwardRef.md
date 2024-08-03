###### (is a built-in react API) lets your component expose a DOM node to parent component with a ref.
(parent node can dome manipulate child node)
#### Parameters

- `props`: The props passed by the parent component.
    
- `ref`: The `ref` attribute passed by the parent component. The `ref` can be an object or a function. If the parent component has not passed a ref, it will be `null`. You should either pass the `ref` you receive to another component, or pass it to useImperativeHandle.
### Exposing a DOM node to the parent component [](https://react.dev/reference/react/forwardRef#exposing-a-dom-node-to-the-parent-component "Link for Exposing a DOM node to the parent component")

By default, each component’s DOM nodes are private. However, sometimes it’s useful to expose a DOM node to the parent—for example, to allow focusing it. To opt in, wrap your component definition into `forwardRef()`. You will receive a ref as the second argument after props. Pass it to the DOM node that you want to expose:

```js
import { forwardRef } from 'react';

const MyInput = forwardRef(function MyInput(props, ref) {
  const { label, ...otherProps } = props;
  return (
    <label>
      {label}
      <input {...otherProps} ref={ref} />
    </label>
  );
});
```
This lets the parent `Form` component access the `<input>` DOM node exposed by `MyInput`:
```js
function Form() {
  const ref = useRef(null);

  function handleClick() {
    ref.current.focus();  //use of ref
  }

  return (
    <form>
      <MyInput label="Enter your name:" ref={ref} />
      <button type="button" onClick={handleClick}>
        Edit
      </button>
    </form>
  );
}
```
This `Form` component passes a ref to `MyInput`. The `MyInput` component _forwards_ that ref to the `<input>` browser tag. As a result, the `Form` component can access that `<input>` DOM node and call [`focus()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/focus) on it.

Keep in mind that exposing a ref to the DOM node inside your component makes it harder to change your component’s internals later. You will typically expose DOM nodes from reusable low-level components like buttons or text inputs, but you won’t do it for application-level components like an avatar or a comment.

![[zz1.png]]