# Activity 1:  CRUD Operations with Postmanm

**Objective:**
To practice performing CRUD operations (Create, Read, Update, Delete) on a RESTful API using Postman with JSONPlaceholder.com as the API endpoint.

**Prerequisites:**
- Postman application installed on your computer
- Registered account on Postman

**Steps:**

1. **Download Postman and Register for an Account:**
   - Visit the Postman website (https://www.postman.com/) and download the Postman application.
   - Install the application on your computer following the installation instructions.
   - Once installed, open Postman and sign in with your registered account credentials. If you don't have an account, you can create one by clicking on "Sign Up."

2. **Create a Collection:**
   - Launch the Postman application.
   - In the left sidebar, click on the "Collections" tab.
   - Click on the "New Collection" button.
   - Enter a name for the collection, such as "My First API," and click "Create."

3. **Make a POST One Request:**
   - Click on the newly created collection to open it.
   - Click on the "Add Request" button.
   - Enter a name for the request, such as "Create One."
   - In the "Request URL" field, enter the endpoint URL for creating a resource on JSONPlaceholder.com: `https://jsonplaceholder.typicode.com/posts`.
   - Select the appropriate HTTP method (POST).
   - Click on the "Body" tab below the URL field.
   - Select "raw" as the body type.
   - In the text area below, enter the JSON data representing the resource you want to create. For example:
     ```json
     {
       "title": "New Post",
       "body": "This is the body of the new post."
     }
     ```
   - Click "Send" to execute the request.

4. **Make a GET ALL Request:**
   - Follow the same steps as above to add another request.
   - Name the request "Get All."
   - Enter the URL for retrieving all resources: `https://jsonplaceholder.typicode.com/posts`.
   - Use the appropriate HTTP method (GET).
   - Click "Send" to execute the request.

5. **Make a GET One Request:**
   - Repeat the steps to add a new request.
   - Name the request "Get One."
   - Enter the URL for retrieving a single resource, including a placeholder for the resource ID: `https://jsonplaceholder.typicode.com/posts/{id}`.
   - Replace `{id}` with the ID of the resource you want to retrieve.
   - Use the appropriate HTTP method (GET).
   - Click "Send" to execute the request.

6. **Make a DELETE One Request:**
   - Repeat the steps to add a new request.
   - Name the request "Delete One."
   - Enter the URL for deleting a resource, including a placeholder for the resource ID: `https://jsonplaceholder.typicode.com/posts/{id}`.
   - Replace `{id}` with the ID of the resource you want to delete.
   - Use the appropriate HTTP method (DELETE).
   - Click "Send" to execute the request.

7. **Make an UPDATE One Request:**
   - Repeat the steps to add a new request.
   - Name the request "Update One."
   - Enter the URL for updating a resource, including a placeholder for the resource ID: `https://jsonplaceholder.typicode.com/posts/{id}`.
   - Replace `{id}` with the ID of the resource you want to update.
   - Use the appropriate HTTP method (PUT or PATCH).
   - Click on the "Body" tab below the URL field.
   - Select "raw" as the body type.
   - In the text area below, enter the updated JSON data for the resource.
   - Click "Send" to execute the request.

8. **Test Requests:**
   - Go through each request in the collection and click "Send" to execute them.
   - Review the responses to ensure they match the expected outcomes for each operation.
   - Pay attention to status codes, response body content, and any error messages.

9. **Review and Debug:**
   - If any of the requests fail or produce unexpected results, review the request configuration and the API documentation.
   - Make any necessary adjustments to the requests or the API code to resolve issues and ensure proper functionality.

10. **Conclusion:**
    - By following these steps and testing the CRUD operations on JSONPlaceholder.com using Postman, you have gained practical experience in working with RESTful APIs and familiarized yourself with basic API testing using Postman. This knowledge is essential for working with APIs in real-world projects.

