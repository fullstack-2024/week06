# Activity D

<!-- Arrow function -->
Write a payment API server with the following the data model:

```js
const paymentSchema = new mongoose.Schema({
  amount: { type: Number, required: true },
  method: { type: String, required: true },
  status: { type: String, required: true }
});
```
