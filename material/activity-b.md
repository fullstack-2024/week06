# Activity B

Write an API server for events. Here's the data model:

```js
const eventSchema = new mongoose.Schema({
  title: { type: String, required: true },
  description: { type: String, required: true },
  date: { type: Date, required: true },
  location: { type: Boolean },
});
```

