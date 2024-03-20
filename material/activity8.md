# Activity 8:

<!-- Arrow function -->
Write a message API server with the following the data model:

```js
const messageSchema = new mongoose.Schema({
  sender: { type: String, required: true },
  recipient: { type: String, required: true },
  content: { type: String, required: true }
});
```