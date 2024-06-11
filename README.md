# Overview

This project aims to equip you with the skills to proficiently use NodeJS for server-side development and to write comprehensive test suites for your applications. By the end of this project, you should be able to explain and demonstrate the following concepts without external help:

## NodeJS Development

- Running JavaScript using NodeJS
- Using NodeJS modules
- Utilizing specific NodeJS modules to read files
- Accessing command line arguments and the environment using process
- Creating a small HTTP server using NodeJS
- Creating a small HTTP server using ExpressJS
- Developing advanced routes with ExpressJS
- Using ES6 with NodeJS and Babel-node
- Enhancing development speed with Nodemon

## Testing with Mocha and Chai

- Writing test suites using Mocha
- Utilizing different assertion libraries (Node or Chai)
- Structuring and presenting long test suites
- Using spies and stubs effectively
- Understanding and implementing hooks
- Performing unit tests with asynchronous functions
- Writing integration tests for a small Node server
 
## Prerequisites

### Before starting, ensure you have the following installed:

- NodeJS (version 12 or higher)
- npm (Node package manager)
- Babel-node
- Nodemon
- Mocha
- Chai
  
## Setup Instructions

### Step 1: Clone the Repository:

```bash
git clone <repository-url>
cd <repository-directory>
```

### Step 2: Install Dependencies:

```bash
npm install
```

### Step 3: Run the Development Server:

- Using NodeJS:

```bash
node server.js
```

- Using Nodemon:

```bash
nodemon server.js
```

### Step 4: Transpile ES6 Code:

```bash
npx babel-node src/index.js
```

### Step 5: Run Tests:

```bash
npm test
```

## Project Structure

```bash
├── src
│   ├── index.js         # Main application entry point
│   ├── server.js        # NodeJS server setup
│   ├── expressServer.js # ExpressJS server setup
│   ├── routes           # ExpressJS routes
│   └── utils            # Utility modules
├── test
│   ├── unit             # Unit tests
│   ├── integration      # Integration tests
│   └── helpers          # Test helpers (spies, stubs, hooks)
├── .babelrc             # Babel configuration
├── package.json         # Project metadata and dependencies
├── README.md            # Project documentation
└── .gitignore           # Git ignore file
```

## Usage Instructions

### Running JavaScript with NodeJS

- To execute a JavaScript file using NodeJS, use:

```bash
node filename.js
```

### Using NodeJS Modules

- Require a module in your JavaScript file:

```js
const fs = require('fs');
```

### Reading Files

- To read a file using a NodeJS module:

```js
const fs = require('fs');
fs.readFile('path/to/file', 'utf8', (err, data) => {
  if (err) throw err;
  console.log(data);
});
```

### Accessing Command Line Arguments

- Use process.argv to access command line arguments:

```js
process.argv.forEach((val, index) => {
  console.log(`${index}: ${val}`);
});
```

### Creating HTTP Servers

- NodeJS:

```js
const http = require('http');
const server = http.createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello, World!\n');
});

server.listen(3000, '127.0.0.1', () => {
  console.log('Server running at http://127.0.0.1:3000/');
});
```

- ExpressJS:

```js
const express = require('express');
const app = express();

app.get('/', (req, res) => {
  res.send('Hello, World!');
});

app.listen(3000, () => {
  console.log('Express server running on port 3000');
});
```

### Advanced Routing with ExpressJS

- Define routes in the routes directory and use them in your Express app:

```js
const router = express.Router();

router.get('/user/:id', (req, res) => {
  res.send(`User ID: ${req.params.id}`);
});

app.use('/api', router);
```

### Using ES6 with Babel-node

- Transpile and run ES6 code:

```bash
npx babel-node src/index.js
```

### Development with Nodemon

- Automatically restart the server on file changes:

```bash
nodemon server.js
```

### Testing Instructions

### Writing Tests with Mocha and Chai

Write your test cases in the test directory.

- Basic Test Example:

```js
const assert = require('chai').assert;

describe('Array', function() {
  it('should return -1 when the value is not present', function() {
    assert.equal([1,2,3].indexOf(4), -1);
  });
});
```

- Run Tests:

```bash
npm test
```

### Using Spies and Stubs

Utilize spies and stubs for more comprehensive testing. Refer to the Mocha and Chai documentation for examples and usage.

### Hooks

```js
beforeEach(() => {
  // setup code
});

afterEach(() => {
  // teardown code
});
```

### Conclusion

By following the instructions and examples provided in this README, you should be able to develop and test NodeJS applications proficiently.
Happy coding!
