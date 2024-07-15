#react
useCallback is a React Hook that lets you cache a function definition between re-renders.
```js
import { useCallback } from 'react';  

export default function ProductPage({ productId, referrer, theme }) { 

const handleSubmit = useCallback((orderDetails) => {  
post('/product/' + productId + '/buy', {  
referrer,  
orderDetails,  
});  
}, [productId, referrer]);
```

During subsequent renders, it will either return an already stored `fn` function from the last render (if the dependencies haven’t changed), or return the `fn` function you have passed during this render.
