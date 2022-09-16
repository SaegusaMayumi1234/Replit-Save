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
```sh
"script": {
  "start": "node index.js"
}
```
