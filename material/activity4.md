# activity 4: Creating an API Server with Express and Mongoose

In this lab, you will learn how to build an API server using Express.js and Mongoose, a MongoDB object modeling tool. By following the steps outlined below, you will create a simple API server capable of performing CRUD (Create, Read, Update, Delete) operations on a MongoDB database.

### Prerequisites
- Node.js installed on your machine.
- Basic understanding of JavaScript and web development concepts.


### Part 1

1. **Create Folder Structure:**
    - Navigate to the `week6` directory.
    - Create a new folder named `lab4`.

2. **Create Files:**
    - Inside the `lab4` folder, create three files: `db.js`, `controller.js`, and `app.js`.

3. **Initialize Node.js Project:**
    - Open your terminal or command prompt.
    - Navigate to the `lab4` directory.
    - Run the command: `npm init -y`
    
4. **Install Dependencies:**
    - While still in the `lab4` directory, run: `npm install mongoose express`

5. **Write `db.js` (Database Connection):**
    - Open the `db.js` file in a text editor.
    - Copy and paste the provided code for connecting to the MongoDB database using Mongoose.
    
```javascript
const mongoose = require("mongoose");

const MONGO_URI = "mongodb://localhost:27017/books";

const connectDB = async () => {
  const conn = await mongoose.connect(MONGO_URI);
  console.log("MongoDB Connected");
};

module.exports = connectDB;
```

6. **Write `controller.js` (CRUD Operations):**
    - Open the `controller.js` file in a text editor.
    - Copy and paste the provided code for defining the `Book` schema and CRUD operations.
    
```javascript
const mongoose = require("mongoose");

const bookSchema = new mongoose.Schema({
  title: { type: String, required: true },
  author: { type: String, required: true },
  genre: { type: String },
});

const Book = mongoose.model("Book", bookSchema);

// Get all Books
const getBooks = async (req, res) => {
  const books = await Book.find({});
  res.status(200).json(books);
};

// Add one Book
const addBook = async (req, res) => {
  const { title, author, genre } = req.body;
  const newBook = new Book({ title, author, genre });
  await newBook.save();
  res.status(201).json(newBook);
};

// Delete Book by ID
const deleteBook = async (req, res) => {
  const { id } = req.params;

  const book = await Book.findByIdAndDelete(id);
  if (!book) {
    return res.status(404).json({ message: "Book not found" });
  }
  res.status(200).json({ message: "Book deleted successfully" });
};

// Delete all Books
const deleteAllBooks = async (req, res) => {
  const result = await Book.deleteMany({}); 
  res
    .status(200)
    .json({ message: `Deleted ${result.deletedCount} books successfully` });
};

module.exports = { getBooks, addBook, deleteBook, deleteAllBooks };
```

7. **Write `app.js` (Express Server):**
    - Open the `app.js` file in a text editor.
    - Copy and paste the provided code for setting up an Express server, defining routes, and integrating with the database.
    
```javascript
const express = require("express");
const connectDB = require("./db");
const { getBooks, addBook, deleteBook, deleteAllBooks} = require("./controller");

const app = express();

app.use(express.json());

// Connect to MongoDB
connectDB();

// Routes
app.get("/books", getBooks);
app.post("/books", addBook);
app.delete("/books/:id", deleteBook);
app.delete("/books", deleteAllBooks);

const PORT = 5000;

// Start the server
app.listen(PORT, () => {
  console.log(`Server is running on port http://localhost:${PORT}`);
});
```

8. **Run the Server:**
    - In the terminal, ensure you are still in the `lab4` directory.
    - Run the command: `node app.js`

10. **Test the API Endpoints:**
    - Use Postman to test the API endpoints.
    - Endpoints include `/books` to get all books, `POST /books` to add a new book,  `DELETE /books/:id` to delete a book by its ID and  `DELETE /books` to delete all books.


## Part 2

Write an API server for pets. Here's the data model:

```js
const petSchema = new mongoose.Schema({
  name: { type: String, required: true },
  species: { type: String, required: true },
  age: { type: Number, required: true },
});
```

### Conclusion
Congratulations! You have successfully built an API server using Express.js and Mongoose. This lab provides a foundational understanding of creating RESTful APIs and working with MongoDB databases in a Node.js environment. You can further enhance this project by adding validation, authentication, and additional CRUD operations as needed.