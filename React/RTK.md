
**Store Configuration:
```js
import { configureStore } from "@reduxjs/toolkit";
import authSlice from "./authSlice";

const store =configureStore({
    reducer:{
        auth:authSlice,
    }
}    
)

export default store;
```

**Slice code:**

```js
import { createSlice } from "@reduxjs/toolkit";

const initialState={
    status:false,
    userData:null
}

const authSlice=createSlice(
    {
    name: "auth",
    initialState,
    reducers:{
        login: (state,action)=>{
            state.status=true;
            state.userData=action.payload;
                    },
        logout:(state)=>{
            state.status=false;
            state.userData=null;
        }

            }
    }
)

export const {login,logout}=authSlice.actions;
export default authSlice.reducer;
```

**Store**:

- Centralized location to manage the entire state of your application.
- Created using `configureStore` in RTK.
- Holds the current state and allows for state updates via dispatched actions.

**Reducer**:
A reducer is a pure function that takes the current state and an action as arguments and returns a new state. It describes how the state should change in response to an action sent to the store

**Slice**:
- A "slice" is a concept in Redux Toolkit that represents a portion of the Redux state.
- Contains an initial state, a reducer, and action creators related to that part of the state.
- Generates action creators and action types for the reducers defined within the slice automatically
-  Each slice manages its own state and has a name that can be used to access its part of the overall Redux state. 

**useDispatch**:
- A React hook provided by RTK to dispatch actions to the Redux store.
- Allows you to trigger state changes by dispatching actions.

**useSelector**:
- A React hook provided by RTK to access the Redux store’s state.
- Allows you to select and use a specific part of the state within your component.
