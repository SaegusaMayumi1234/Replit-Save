# Replit-Save
A repo to save some methods for replit like updating node and keeping it always run


## How to update replit nodejs
1. Execute Code below in shell
```sh
npm init -y && npm i --save-dev node@18 && npm config set prefix=$(pwd)/node_modules/node && export PATH=$(pwd)/node_modules/node/bin:$PATH
```
2. Add this line below in .replit file by showing hidden file
```sh
run = "npm start"
```
3. Add this to package.json
```json
"script": {
  "start": "node index.js"
}
```
4. Check the version by execute this command on shell
```sh
node --version
```
Or adding this line into your main js file
```js
console.log(process.version)
```

## How to keep replit running
1. Add this code below to any of your file
```js
const express = require('express');
const app = express();

app.use(express.urlencoded({ extended: true, limit: '50mb' }))
app.use(express.json({limit: '50mb'}));
// app.use(express.urlencoded({limit: '50mb'}));

app.all('/', (req, res)=>{
  res.status(200).json({
    status: 200
  })
})

function keepAlive(){
  app.listen(3000, () => {
    console.log("Server is Ready!")
  });
}

/* making this in another file
 * module.exports = keepAlive; //Add this if you want to adding this into another fil
 * // another file:
 * keepAlive() //Add this to another file after importing this file
 */
 
// or running this in current file
keepAlive()
```
2. Make an account in robouptime and make a monitor for your replit link
