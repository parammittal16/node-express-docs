# node-express-docs

[![npm version](https://badge.fury.io/js/node-express-docs.svg)](https://badge.fury.io/js/node-express-docs)

[![NPM](https://nodei.co/npm/node-express-docs.png?downloads=true&downloadRank=true&stars=true)](https://nodei.co/npm/node-express-docs/)
### NO NEED TO ASK ENDPOINTS FROM YOUR BACKEND DEVELOPER EVERY MINUTE

A node package used to display all the registered endpoints of the project and send them with password protection to anyone using the API.

## How To Install
It is just a development dependency
```
npm install node-express-docs --save-dev
```
Or it can be used as a full dependency  
```
npm install node-express-docs --save
```
## How to use
```
const showEndpoints = require('node-express-docs');

```
In main app.js/index.js/server.js

Just After you use your routes middlewares like 
```
app.use('/', RouteXYZ);
```
Paste the code below
```
app.get("/__docs", (req, res, err)=> {
  if(req.query.pass === 'YOUR_SECRET'){
    res.send(showEndpoints(app));
  }
  else{
    res.send("<html><body><h2>UnAuthorized</h2></body></html>")
  }
});
```
## Output
```
Got to 

localhost:3000/__docs?pass=YOUR_SECRET 

to see your endpoints.
```
You can also set a Secret by replacing 'YOUR_SECRET' and share the pass with your Front-end co-workers.
THANKS
