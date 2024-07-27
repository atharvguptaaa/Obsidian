### Context in React: 
Context provides a <font color="#2DC26B">way to</font> <font color="#2DC26B">pass data through the component tree without having to pass props down manually at every level</font>. This is particularly useful for data that needs to be accessible by many components at different nesting levels, such as theme settings, user authentication data, language preferences, etc.

**Creating a Context**
```js
//userContext.js
import React from "react"
const UserContext= React.createContext()
export default UserContext
```
To make the context value available to a component tree, you use the <font color="#2DC26B">Provider </font>component that comes with every context object. You can <font color="#2DC26B">set the value</font> that needs to be accessible by all consuming components:
```js
//userContextProvider.jsx
import React, { useState } from "react";
import UserContext from "./UserContext";

const UserContextProvider=({childComponents})=>{
    const [user, setUser] = useState(null) 
        return(
        <UserContext.Provider value={{user,setUser}}> //passed an object
        {children} //wraps child components
        </UserContext.Provider>
    )//code snippet defines a React component called UserContextProvider
}
export default UserContextProvider
```
**Consuming Context with useContext()**: to consume the context value, you can use the useContext hook inside any functional component
```js 
//Login.jsx
import React, {useState,useContext} from 'react'
import UserContext from '../context/UserContext'

function Login() {
    const [username,setUsername]=useState('')
    const [password, setPassword] = useState('')

    const {setUser}=useContext(UserContext)
    const handleSubmit=(e)=>{
        e.preventDefault()
        setUser({username,password})
    }   
  return (
    <div>
        <h2>Login</h2>  
    <input type="text" value={username}
     onChange={(e)=>setUsername(e.target.value)}
     placeholder='username' />

    <input type="text" value={password}
     onChange={(e)=>setPassword(e.target.value)}
     placeholder='password' />

    <button onClick={handleSubmit}>Submit</button>
    </div>
  )
}
export default Login
```

```js 
//Profile.jsx
import React, { useContext } from 'react'
import UserContext from '../context/UserContext'

function Profile() {
    const {user}=useContext(UserContext)

   if (!user) return <div>please login</div> 
   
   return <div>Welcome {user.username}. Your password is {user.password}</div>
}
export default Profile
```
**Providing Context Value**
```js
//App.jsx
import './App.css'
import Login from './components/Login'
import Profile from './components/Profile'
import UserContextProvider from './context/UserContextProvider'

function App() {
  return (
    <UserContextProvider>
      <Login/>
      <Profile/>
    </UserContextProvider>
  )
}
export default App

```