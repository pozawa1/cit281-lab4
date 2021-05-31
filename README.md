# Objectives
1. Create initial Fastify Node.js web server
2. Add Fastify to project using npm, and test using Visual Studio Code (VSCode)

# Technologies Used
- Terminal
- VSCode

# Part 1
Create a folder called lab-04 in your cit281/p4 folder.
```
// Require the Fastify framework and instantiate it
const fastify = require("fastify")();
// Handle GET verb for / route using Fastify
// Note use of "chain" dot notation syntax
fastify.get("/", (request, reply) => {
  reply
    .code(200)
    .header("Content-Type", "text/text; charset=utf-8")
    .send("<h1>Hello from Lab 4!</h1>");
});
// Start server and listen to requests using Fastify
const listenIP = "localhost";
const listenPort = 8080;
fastify.listen(listenPort, listenIP, (err, address) => {
  if (err) {
    console.log(err);
    process.exit(1);
  }
  console.log(`Server listening on ${address}`);
});
```

# Part 2
Initialize the folder as a Node.js project.

# Part 3
Add Fastify to project using npm.

# Part 4
Add git repo, exclude node_modules folder from git, and make commits. 

# Part 5
Fix MIME error, test, and commit.
```
.header("Content-Type", "text/html; charset=utf-8")
```

# Part 6
Add a second route with query parameters, test, and commit.
```
// Route for /name
fastify.get("/name", (request, reply) => {
  const {first, last} = request.query;

  const name = first && last ? `${first} ${last}` : `Guest`;

  reply
    .code(200)
    .header("Content-Type", "text/html; charset=utf-8")
    .send(`<h1>Hello, ${name}</h1>`);
});

// Start server and listen to requests using Fastify
const listenIP = "localhost";
const listenPort = 8080;
fastify.listen(listenPort, listenIP, (err, address) => {
  if (err) {
    console.log(err);
    process.exit(1);
  }
  console.log(`Server listening on ${address}`);
});
```

![lab-04-guest](https://user-images.githubusercontent.com/83732149/120247575-d8665e80-c228-11eb-9ead-05ecb99e4412.png)

