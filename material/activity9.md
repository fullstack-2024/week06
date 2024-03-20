# Activity 9:

### Part 1
<!-- Arrow function -->
Write a order API server with the following the data model:

```js
const orderSchema = new mongoose.Schema({
  customer: { type: String, required: true },
  totalAmount: { type: Date, required: true },
  duration: { type: Number, required: true },
  products: { type: String },
  status: { type: String }
});
```

### Part 2

Push this activity to GitHub. You can follow [this guideline](./git-instructions.md)