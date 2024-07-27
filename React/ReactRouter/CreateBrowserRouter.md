```js
import { createBrowserRouter, RouterProvider } from 'react-router-dom';  
import { Home, Layout, About, Contact, User, GitHub } from './Components'
  
const router = createBrowserRouter([
  {
    path: "/",
    element:<Layout />,
    children:[
	      {
	        path: "Home",
	        element:
	      },
	      {
	        path: "About",
	        element:
	      },
	      {
	        path: "Contact",
	        element:
	      }
    ]
  }
])
  
const App = () => {  
return <RouterProvider router={router} />;  
};  
export default App;
```

## or

```js
const router= createBrowserRouter(
      createRoutesFromElements(
        <Route path="/" element={<Layout />} >
  
	        <Route path="home" element= {<Home/>} />
	        <Route path="about" element= {<About/>} />
	        <Route path="contact" element= {<Contact />} />
	        <Route path="user/:userid" element= {< User/>} />
	        <Route path="github" element= {<GitHub/>} />
        </Route>
      )
)
```
