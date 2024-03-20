# Activity 5:

### Step 1: Setup

1. Create a folder named `lab#` (replace `#` with the lab number) in this week's folder.
2. Navigate to the `lab#` folder in your terminal.
3. Initialize the folder as an npm project by running the command:
   ```
   npm init -y
   ```
   This will create a `package.json` file.
4. Install the necessary dependencies by running:
   ```
   npm install express mongoose
   ```

### Step 2: Create Files

1. Inside the `lab#` folder, create four files: `db.js`, `app.js`, `controller.js`, and `model.js`.

### Step 3: Add Content to Files

1. Open `db.js` and add the following content:

```javascript
const mongoose = require("mongoose");

const MONGO_URI = "mongodb://localhost:27017/fullstack-course";

const connectDB = async () => {
  const conn = await mongoose.connect(MONGO_URI);
  console.log("MongoDB Connected");
};

module.exports = connectDB;
```

2. Open `model.js` and add the following content:

```javascript
const mongoose = require('mongoose');

const goalSchema = new mongoose.Schema({
  title: { type: String, required: true },
  description: { type: String, required: true },
  targetDate: { type: Date, required: true },
  achieved: { type: Boolean },
});

module.exports = mongoose.model('Goal', goalSchema);
```

3. Open `controller.js` and add the following content:

```javascript
const Goal = require("./model");

// get all Goals
const getGoals = async (req, res) => {
  const goals = await Goal.find({});
  res.status(200).json(goals);
};

// Add one Goal
const addGoal = async (req, res) => {
  const { title, description, targetDate, achieved } = req.body;

  const newGoal = new Goal({ title, description, targetDate, achieved });
  await newGoal.save();
  res.status(201).json(newGoal);
};

// Get Goal by ID
const getGoal = async (req, res) => {
  const { id } = req.params;

  const goal = await Goal.findById(id);
  if (!goal) {
    return res.status(404).json({ message: "Goal not found" });
  }
  res.status(200).json(goal);
};

// Delete Goal by ID
const deleteGoal = async (req, res) => {
  const { id } = req.params;

  const goal = await Goal.findByIdAndDelete({ _id: id });
  if (!goal) {
    return res.status(404).json({ message: "Goal not found" });
  }
  res.status(200).json({ message: "Goal deleted successfully" });
};

// Delete all Books
const deleteAllGoals = async (req, res) => {
  const result = await Goal.deleteMany({});
  res
    .status(200)
    .json({ message: `Deleted ${result.deletedCount} books successfully` });
};

// Update Goal by ID
const updateGoal = async (req, res) => {
  const { id } = req.params;
  const updatedGoal = req.body;
  const goal = await Goal.findOneAndUpdate({ _id: id }, updatedGoal);
  if (!goal) {
    return res.status(404).json({ message: "Goal not found" });
  }
  res.status(200).json(goal);
};

module.exports = {
  getGoals,
  addGoal,
  getGoal,
  deleteGoal,
  deleteAllGoals,
  updateGoal,
};
```

4. Open `app.js` and add the following content:

```javascript
const express = require("express");
const app = express();

const connectDB = require("./db");
const {
  getGoals,
  addGoal,
  getGoal,
  updateGoal,
  deleteGoal,
  deleteAllGoals,
} = require("./controller");

//Important: will be discussed next week
app.use(express.json());

// Connect to MongoDB
connectDB();

// Routes
// GET all Goals
app.get("/goals", getGoals);

// POST a new Goal
app.post("/goals", addGoal);

// GET a single Goal
app.get("/goals/:id", getGoal);

// Update Goal using PUT
app.put("/goals/:id", updateGoal);

// DELETE a Goal
app.delete("/goals/:id", deleteGoal);

// DELETE all Goal
app.delete("/goals", deleteAllGoals);

const PORT = 4000;

// Start the server
app.listen(PORT, () => {
  console.log(`Server is running on port http://localhost:${PORT}`);
});
```

### Step 4: Start the Server

1. In the terminal, start the server by running:
   ```
   node app.js
   ```
   This will start the server at port 4000.

### Step 5: Test Endpoints Using Postman

1. Open Postman and create a collection with the name of the lab (e.g., `lab#`).
2. Create the following requests within the collection:
   - POST: Create one item
   - GET: Get all data
   - GET: Get one item
   - PUT: Update one item
   - DELETE: Delete one item
   - DELETE: Delete all items
3. For POST and PUT Requests

When making POST and PUT requests to your Express server, it's essential to include the necessary data in the request body in JSON format. This data typically represents the resource you want to create or update.
   - In a POST request, you are creating a new resource on the server. Therefore, you need to include all the relevant data for creating this resource in the request body.
   - Example of a POST request body in JSON format:
```json
  {
    "title": "title1",
    "description": "description1",
    "targetDate": "2024-03-21T08:26:29.692Z",
    "achieved": false
  }
```

   - In a PUT request, you are updating an existing resource on the server. Therefore, you need to include all the relevant data for updating this resource in the request body.
   - Example of a PUT request body in JSON format: 
```json
  {
    "title": "title1",
    "description": "description1",
    "targetDate": "2024-03-17T08:26:29.692Z",
    "achieved": true
  }
```

4. For GET, PUT, and DELETE Requests

When making GET, PUT, and DELETE requests that target a specific item, it's crucial to provide the correct parameter in the path. This parameter typically identifies the specific resource you want to retrieve, update, or delete.

   - In a GET request to retrieve a specific item, you need to include the unique identifier of the item as a parameter in the URL path.
   - Example of a GET request to retrieve a specific item:
```
GET /goals/:id
```

Here, `:id` is a placeholder for the unique identifier of the item you want to retrieve.


   - In a PUT request to update a specific item, you also need to include the unique identifier of the item as a parameter in the URL path.
   - Example of a PUT request to update a specific item:
```
PUT /goals/:id
```

   - In a DELETE request to delete a specific item, you need to include the unique identifier of the item as a parameter in the URL path.
   - Example of a DELETE request to delete a specific item: 
```
DELETE /goals/:id
```

