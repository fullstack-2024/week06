# Activity 6:

### Part 1

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

const inventorySchema = new mongoose.Schema({
  name: { type: String, required: true },
  description: { type: String, required: true },
  quantity: { type: Number, required: true },
  price: { type: Number, required: true },
});

module.exports = mongoose.model('Inventory', inventorySchema);
```

3. Open `controller.js` and add the following content:

```javascript
// Add content here
```

4. Open `app.js` and add the following content:

```javascript
// Add content here
```

### Step 4: Start the Server

1. In the terminal, start the server by running:
   ```
   node app.js
   ```
   This will start the server at port 4000.

### Step 5: Test Endpoints Using Postman

> To review how to test APIs with Postman, refer to [this guideline](./postman.md)


### Part 2

Push this activity to GitHub. You can follow [this guideline](./git-instructions.md)