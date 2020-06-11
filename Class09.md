# Class 09

## mongoose instance methods
- Mongoose schemas/documents come with several built-in methods. However, custom methods can be created.
```js
const productSchema = new mongoose.Schema({
  name: {
    type: String,
    required: true,
    maxlength: 100
  },
  description: {
    type: String,
    required: true,
    maxlength: 200
  },
  size: {
    type: Number,
    required: true
  },
});

// ('schemaName').methods.('method name') = function (cb) {

}
productSchema.methods.findSimilarSizes = function(cb) {
  return mongoose.model('Animal').find({ type: this.size }, cb)
};
```
## monogoose static methods
- Static methods can be called in a similar way. HOWEVER, do not use arrow functions to declare them (we lose this).

```js
const productSchema = new mongoose.Schema({
  name: {
    type: String,
    required: true,
    maxlength: 100
  },
  description: {
    type: String,
    required: true,
    maxlength: 200
  },
  size: {
    type: Number,
    required: true
  },
});

productSchema.static.('functionName', function(size) {
  return this.find({ size })
}
```

## mongoose middleware
- middleware: functions that are passed during execution of async functions.
### Four Types of Middleware
1. document: 'this' refers to the document
1. model: 'this' refers to the model.
1. aggregate: executes when you call exec() on an aggregate object. 'this' refers to aggregation object.
1. query: 'this' refers to the query