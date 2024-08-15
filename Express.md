library that lets you create HTTP Servers

Basic http server made using express. On accessing localhost 3000 it will respond by displaying 'hi there'.

```js
const express=require("express");
const app=express();
app.get("/",function(req,res){
    res.send("hi there")
})

app.listen(3000); //port
```