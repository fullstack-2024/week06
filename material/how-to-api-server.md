# Tips to write API server

1. **Start with Database Connection:**
   - Begin by establishing a connection to the database using the code provided in the labs. Ensure that the connection is successful before proceeding.

2. **Create Data Model:**
   - Define your data model using Mongoose schema. 
   - Follow the naming convention: capitalize the model name (e.g., Book, Car) and let Mongoose handle collection naming (plural, lowercase).
   - Export the model to use it in other parts of your application.

3. **Write Controller Functions:**
   - Import the model into your controller file.
   - Write controller functions to handle various operations such as fetching all items (e.g., `getAll()`). Follow camelCase naming convention for function names.
   - Export each controller function for use in other parts of your application.

4. **Implement Endpoints in the App:**
   - Utilize starter code provided or write your own setup code for Express.
   - Import the controller functions, especially `getAll()`.
   - Define the endpoint to fetch data and link it to the corresponding controller function.
   - Start the server and verify that `getAll()` works as expected using Postman.

5. **Test Each Handler:**
   - After verifying `getAll()`, stop the server and proceed to implement other controller functions.
   - Write controller functions for adding one item (e.g., `addOne()`), deleting one item (e.g., `deleteOne()`), updating one item (e.g., `updateOne()`), getting one item (e.g., `getOne()`), and deleting all items (e.g., `deleteAll()`).

6. Follow the same pattern as before: import the controller function, define the corresponding endpoint, start the server, test with Postman, and stop the server.

7. **Use Mongoose Methods:**

----

- **Get All Items:**
   - To retrieve all items, you'll typically use the `find()` method provided by Mongoose.
   - Import the relevant model into your controller file.
   - Define a function (e.g., `getAll`) in your controller to handle fetching all items.
   - Use the `find()` method to query all items from the collection.
   - Handle scenarios where no items are found and respond accordingly.
   - Export the `getAll` function from your controller.

- **Add One Item:**
   - Adding one item involves creating a new document using the model's constructor function and then saving it to the database.
   - Import the relevant model into your controller file.
   - Define a function (e.g., `addOne`) in your controller to handle adding one item.
   - Extract the data for the new item from the request body.
   - Create a new document using the model's constructor function with the extracted data.
   - Use the `save()` method to save the new document to the database.
   - Handle errors or validation failures during the save operation.
   - Export the `addOne` function from your controller.


- **Delete One Item:**
   - To delete one item, you'll typically use the `findByIdAndDelete()` method provided by Mongoose.
   - In your controller, import the relevant model and define a function (e.g., `deleteOne`) to handle the deletion of one item.
   - Within the `deleteOne` function, you'll extract the item's ID from the request parameters.
   - Then, use the `findByIdAndDelete()` method to find and delete the item based on its ID.
   - Ensure to handle scenarios where the item is not found and respond with an appropriate status code and message.
   - Export the `deleteOne` function from your controller.

- **Update One Item:**
   - For updating one item, you'll typically use the `findByIdAndUpdate()` method provided by Mongoose.
   - Similar to deletion, import the relevant model and define a function (e.g., `updateOne`) in your controller.
   - Extract the item's ID from the request parameters and the updated data from the request body.
   - Use the `findByIdAndUpdate()` method to find the item based on its ID and update it with the provided data.
   - Handle scenarios where the item is not found and respond accordingly.
   - Export the `updateOne` function from your controller.

- **Delete All Items:**
   - Deleting all items involves using the `deleteMany()` method provided by Mongoose.
   - Import the relevant model and define a function (e.g., `deleteAll`) in your controller to handle the deletion of all items.
   - Use the `deleteMany()` method to delete all items from the collection.
   - Ensure to handle errors or scenarios where deletion fails.
   - Export the `deleteAll` function from your controller.

- **Get One Item:**
   - To retrieve one item, you'll typically use the `findById()` method provided by Mongoose.
   - Import the relevant model and define a function (e.g., `getOne`) in your controller to handle fetching one item.
   - Extract the item's ID from the request parameters.
   - Use the `findById()` method to find the item based on its ID.
   - Handle scenarios where the item is not found and respond accordingly.
   - Export the `getOne` function from your controller.

