# Activity C

### Part 1

Write an API server for feedback. Here's the data model:

```js
const feedbackSchema = new mongoose.Schema({
  sender: { type: String, required: true },
  message: { type: String, required: true },
  rating: { type: Number, required: true },
});
```

### Part 2

Push this activity to GitHub. You can follow [this guideline](./git-instructions.md)