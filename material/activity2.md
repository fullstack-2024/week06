# Activity 2


## Part 1/2:  Getting Started with Express.js

**Objective:**
To set up a basic Express.js server and learn how to start and stop the server.

**Prerequisites:**
- Node.js installed on your computer
- Basic understanding of JavaScript and command line usage

**Steps:**

1. **Create a Directory:**
   - Open your terminal or command prompt.
   - Navigate to the week6 folder where you want to create the lab2a directory.
   - Execute the following command to create a new directory named "lab1":
     ```
     mkdir week6/lab2a
     ```

2. **Initialize Node.js Project:**
   - Navigate into the "lab1" directory:
     ```
     cd week6/lab2a
     ```
   - Initialize a new Node.js project with default settings by running:
     ```
     npm init -y
     ```

3. **Install Express.js:**
   - Install the Express.js package using npm:
     ```
     npm install express
     ```

4. **Create a Simple Server:**
   - Create a new file named "controller1.js" in the "lab2a" directory.
   - Open "controller1.js" in a text editor.
   - Write the following code
```javascript
const getRoot = (req, res) => {
  res.json({ message: "I am endpoint get /" });
};

module.exports = { getRoot };
```
   - Create a new file named "app.js" in the "lab2a" directory.
   - Open "app.js" in a text editor.
   - Write the following code to create a simple Express server that responds with "Hello, World!" when accessed:
```javascript
const express = require("express");
const app = express();

const { getRoot } = require('./controller1'); // getRoot is imported

app.get('/', getRoot); // getRoot is used as a callback

const port = 3001;
// Start the server
app.listen(port, () => {
  console.log(`Server is running on port http://localhost:${port}`);
});
```

5. **Start the Server:**
   - In your terminal, navigate to the "lab2a" directory if you're not already there.
   - Start the Express server by running the following command:
     ```
     node app.js
     ```

6. **Visit localhost:3001:**
   - Open your web browser.
   - Enter the following URL in the address bar: `http://localhost:3001`.
   - You should see the message "Hello, World!" displayed in the browser window.

7. **Stop the Server:**
   - To stop the server, return to your terminal.
   - Press `Ctrl + C` to terminate the server process.

## Part 2/2: Mock Server

**Steps:**

1. **Create a Directory:**
   - Open your terminal or command prompt.
   - Navigate to the week6 folder where you want to create the lab2b directory.
   - Execute the following command to create a new directory named "lab2b":
     ```
     mkdir week6/lab2b
     ```

2. **Initialize Node.js Project:**
   - Navigate into the "lab1" directory:
     ```
     cd week6/lab2b
     ```
   - Initialize a new Node.js project with default settings by running:
     ```
     npm init -y
     ```

3. **Install Express.js:**
   - Install the Express.js package using npm:
     ```
     npm install express
     ```

4. **Create a Simple Server:**
   - Create a new file named "controller2.js" in the "lab2b" directory.
   - Open "controller2.js" in a text editor.
   - Write the following code
```javascript
// controller1.js
const getEndpoint1 = (req, res) => {
  res.json({ message: "I am endpoint get /endpoint1" });
};

// controller2.js
const getEndpoint2 = (req, res) => {
  res.json({ message: "I am endpoint get /endpoint2" });
};

// controller3.js
const getEndpoint3 = (req, res) => {
  res.json({ message: "I am endpoint get /endpoint3" });
};

// controller4.js
const getEndpoint4 = (req, res) => {
  res.json({ message: `I am endpoint get /endpoint3/${req.params.something}` });
};

// controller5.js
const getRoot = (req, res) => {
  res.json({ message: "I am endpoint get /" });
};

module.exports = {
  getEndpoint1,
  getEndpoint2,
  getEndpoint3,
  getEndpoint4,
  getRoot,
};
```
   - Create a new file named "app.js" in the "lab2b" directory.
   - Open "app.js" in a text editor.
   - Write the following code to create a simple Express server that responds with "Hello, World!" when accessed:
```javascript
const express = require("express");
const app = express();
const port = 3001;

// Import controllers
const { getEndpoint1 } = require("./controller2");
const { getEndpoint2 } = require("./controller2");
const { getEndpoint3 } = require("./controller2");
const { getEndpoint4 } = require("./controller2");
const { getRoot } = require("./controller2");

// Define routes
app.get("/", getRoot);
app.get("/endpoint1", getEndpoint1);
app.get("/endpoint2", getEndpoint2);
app.get("/endpoint3", getEndpoint3);
app.get("/endpoint3/:something", getEndpoint4);

// Start the server
app.listen(port, () => {
  console.log(`Server is running on port http://localhost:${port}`);
});
```

5. **Start the Server:**
   - In your terminal, navigate to the "lab2b" directory if you're not already there.
   - Start the Express server by running the following command:
     ```
     node app.js
     ```

6. **Test endpoints**
   - Open your web browser.
     - Enter the following URL in the address bar: `http://localhost:3001`. You should see the message "Hello, World!" displayed in the browser window.
     - Enter the following URL in the address bar: `http://localhost:3001/endpoint1`
     - Enter the following URL in the address bar: `http://localhost:3001/endpoint2`   
     - Enter the following URL in the address bar: `http://localhost:3001/endpoint3`
     - Enter the following URL in the address bar: `http://localhost:3001/endpoint3/foo`
     - Enter the following URL in the address bar: `http://localhost:3001/endpoint3/bar`     
   - Open POSTMAN and make a GET request to the followings path: 
     - http://localhost:3001
     - http://localhost:3001/endpoint1
     - http://localhost:3001/endpoint2
     - http://localhost:3001/endpoint3
     - http://localhost:3001/endpoint3/foo
     - http://localhost:3001/endpoint3/bar

7. **Stop the Server:**
   - To stop the server, return to your terminal.
   - Press `Ctrl + C` to terminate the server process.