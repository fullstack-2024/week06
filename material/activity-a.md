# Activity A

Write an API server for contacts. Here's the data model:

```js
const contactSchema = new mongoose.Schema({
  firstName: { type: String, required: true },
  lastName: { type: String, required: true },
  email: { type: String, required: true },
  phone: { type: String },
  address: { type: String },
});
```

