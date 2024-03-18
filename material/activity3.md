# Activity 3

## Part 1/2

**Steps:**

1. **Create a Directory:**
   - Open your terminal or command prompt.
   - Navigate to the week6 folder where you want to create the lab3 directory.
   - Execute the following command to create a new directory named "lab3":
     ```
     mkdir week6/lab3
     ```

2. **Initialize Node.js Project:**
   - Navigate into the "lab1" directory:
     ```
     cd week6/lab3
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
   - Create a new file named "controller3.js" in the "lab3" directory.
   - Open "controller3.js" in a text editor.
   - Write the following code
```javascript
// controller.js

// Create operation
const createItem = (req, res) => {
  res.json({ message: "Endpoint create called" });
};

// Read operation
const getAllItems = (req, res) => {
  res.json({ message: "Endpoint getAll called" });
};

// Read operation
const getOneItem = (req, res) => {
  res.json({ message: `I am endpoint get /get/${req.params.id}` });
};

// Update operation
const updateItem = (req, res) => {
  res.json({ message: `I am endpoint update /update/${req.params.id}` });
};

// Delete operation
const deleteItem = (req, res) => {
  res.json({ message: `I am endpoint delete /delete/${req.params.id}` });
};

module.exports = {
  createItem,
  getOneItem,
  getAllItems,
  updateItem,
  deleteItem,
};
```
   - Create a new file named "app.js" in the "lab3" directory.
   - Open "app.js" in a text editor.
   - Write the following code to create a simple Express server that responds with "Hello, World!" when accessed:
```javascript
const express = require("express");
const app = express();
const port = 3001;

// Import controllers
const {
  createItem,
  getOneItem,
  getAllItems,
  updateItem,
  deleteItem,
} = require("./controller3");

// Routes
app.post("/create", createItem);
app.get("/get", getAllItems);
app.get("/get/:id", getOneItem);
app.put("/update/:id", updateItem);
app.delete("/delete/:id", deleteItem);

// Start the server
app.listen(port, () => {
  console.log(`Server is running on port http://localhost:${port}`);
});
```

5. **Start the Server:**
   - In your terminal, navigate to the "lab3" directory if you're not already there.
   - Start the Express server by running the following command:
     ```
     node app.js
     ```

6. **Test endpoints**    
   - Open POSTMAN and test all operations: GET, POST, PUT and DELETE
   - Follow this [guideline](./Instructions-postman.md)

7. **Stop the Server:**
   - To stop the server, return to your terminal.
   - Press `Ctrl + C` to terminate the server process.

## Part 2/2

Push this activity to GitHub. You can follow [this guideline](./git-instructions.md)