# Activity 7:

<!-- Arrow function -->
Write a location API server with the following the data model:

```js
const locationSchema = new mongoose.Schema({
  name: { type: String, required: true },
  address: { type: String, required: true },
  latitude: { type: Number, required: true },
  longitude: { type: Number }
});
```