1.  npm init -y

2.  npm install json-server

3.  create a db.json file
    and put some dummy data

4.  check of json server run locally
    json-server --watch db.json

5.  create a server.js file

const jsonServer = require("json-server");
const server = jsonServer.create();
const router = jsonServer.router("db.json");
const middlewares = jsonServer.defaults();

server.use(middlewares);
server.use("", router);
server.listen(process.env.PORT || 5000, () => {
console.log("JSON Server is running");
});

6.  change the path in package.json file
    "main": "server.js"

7.  put it in script tag to run the file
    "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start" : "node server.js"
    },
