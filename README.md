1.  npm init -y

2.  npm install json-server json-serve cors

3.  npm install -D nodemon

4.  After the installation, create a new file: index.js. This is the entry point for the json-serve. Add the following inside the file:

const jsonServer = require('json-server')
const cors = require('cors')
const path = require('path')

const server = jsonServer.create()
const router = jsonServer.router(path.join(\_\_dirname, 'db.json'))
const middlewares = jsonServer.defaults()

server.use(cors())
server.use(jsonServer.bodyParser)
server.use(middlewares)
server.use(router)

const PORT = 8000

server.listen(PORT, () => {
console.log(`JSON Server is running on http://localhost:${PORT}`)
})

5. The mock server is ready to run, but let's add some scripts in package.json:

"scripts": {
"start": "node index.js",
"dev": "nodemon index.js"
},

6.  npm run start

7.  db.json

{
"feedback": [
{
"id": 1,
"rating": 10,
"user_name": "Tony Stark",
"text": "You are the ironman of this world"
},
{
"id": 2,
"rating": 9,
"user_name": "Bruce Wayne",
"text": "You are the batman of this world"
},
{
"id": 3,
"rating": 8,
"user_name": "Peter Parker",
"text": "You are the spiderman of this world"
}
]
}
