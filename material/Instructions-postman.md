**Instructions**

**Objective:**
To practice testing the CRUD (Create, Read, Update, Delete) operations of an Express.js API using Postman.

**Prerequisites:**
- Postman application installed on your computer
- Knowledge of CRUD operations
- Basic understanding of JSON format

**Steps:**

1. **Create a Postman Collection:**
   - Open the Postman application.
   - Click on the "Collections" tab in the left sidebar.
   - Click on the "New Collection" button.
   - Enter a name for the collection, such as "My API," and click "Create."

2. **Make a POST Request:**
   - Click on the newly created collection to open it.
   - Click on the "Add Request" button.
   - Enter a name for the request, such as "Create Item."
   - Set the request method to POST.
   - Enter the request URL: `http://localhost:3001/create`.
   - Go to the "Body" tab.
   - Select "raw" as the body type.
   - In the text area below, enter the JSON data representing the item you want to create.
   - Click "Send" to execute the request.

3. **Make a GET ALL Request:**
   - Follow the same steps as above to add another request.
   - Name the request "Get All Items."
   - Set the request method to GET.
   - Enter the request URL: `http://localhost:3001/get`.
   - Click "Send" to execute the request.

4. **Make a GET One Request:**
   - Add a new request to the collection.
   - Name the request "Get One Item."
   - Set the request method to GET.
   - Enter the request URL with a specific item ID: `http://localhost:3001/get/1` (replace `1` with an existing item ID).
   - Click "Send" to execute the request.

5. **Make a DELETE One Request:**
   - Add another request to the collection.
   - Name the request "Delete One Item."
   - Set the request method to DELETE.
   - Enter the request URL with a specific item ID: `http://localhost:3001/delete/1` (replace `1` with the ID of the item you want to delete).
   - Click "Send" to execute the request.

6. **Make an UPDATE One Request:**
   - Add a new request to the collection.
   - Name the request "Update One Item."
   - Set the request method to PUT or PATCH (depending on your API).
   - Enter the request URL with a specific item ID: `http://localhost:3001/update/1` (replace `1` with the ID of the item you want to update).
   - Go to the "Body" tab.
   - Select "raw" as the body type.
   - In the text area below, enter the updated JSON data for the item.
   - Click "Send" to execute the request.

7. **Review Responses:**
   - Review the responses of each request to ensure they match the expected outcomes for each CRUD operation.
   - Pay attention to status codes, response body content, and any error messages.

8. **Conclusion:**
   - By following these steps and testing the Express.js API endpoints with Postman, you have gained practical experience in testing CRUD operations on a RESTful API.
   - You have verified that the API functions correctly and handles various types of requests appropriately.

You have now successfully completed the lab exercises for testing Express.js API endpoints with Postman. Keep practicing and exploring more advanced features of Postman to enhance your API testing skills.