
# Testing Endpoints Using Postman

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
   - Example of a POST request body in JSON format: (**Replace the JSON content in the requests with data that corresponds to the structure defined in your data model.**) 

```json
{
  "title": "Sample Title",
  "description": "This is a sample description",
  "price": 19.99
}
```

   - In a PUT request, you are updating an existing resource on the server. Therefore, you need to include all the relevant data for updating this resource in the request body.
   - Example of a PUT request body in JSON format: (**Replace the JSON content in the requests with data that corresponds to the structure defined in your data model.**) 

```json
{
  "title": "Updated Title",
  "description": "This is an updated description",
  "price": 29.99
}
```

4. For GET, PUT, and DELETE Requests

When making GET, PUT, and DELETE requests that target a specific item, it's crucial to provide the correct parameter in the path. This parameter typically identifies the specific resource you want to retrieve, update, or delete.

   - In a GET request to retrieve a specific item, you need to include the unique identifier of the item as a parameter in the URL path.
   - Example of a GET request to retrieve a specific item: (**Replace the placeholder `/api/items/` with the actual endpoint path that corresponds to the resource you are interacting with. Ensure that the updated path accurately reflects the desired endpoint on the server.**) 

```
GET /api/items/:id
```

Here, `:id` is a placeholder for the unique identifier of the item you want to retrieve.


   - In a PUT request to update a specific item, you also need to include the unique identifier of the item as a parameter in the URL path.
   - Example of a PUT request to update a specific item: (**Replace the placeholder `/api/items/` with the actual endpoint path that corresponds to the resource you are interacting with. Ensure that the updated path accurately reflects the desired endpoint on the server.**) 
   
```
PUT /api/items/:id
```

   - In a DELETE request to delete a specific item, you need to include the unique identifier of the item as a parameter in the URL path.
   - Example of a DELETE request to delete a specific item: (**Replace the placeholder `/api/items/` with the actual endpoint path that corresponds to the resource you are interacting with. Ensure that the updated path accurately reflects the desired endpoint on the server.**) 

```
DELETE /api/items/:id
```

