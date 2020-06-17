# Class 13 Reading: Mongo Aggregations

## Aggregation Pipeline:
- MongoDB aggregation consists of stages. Each stage transforms the document in some way.
- A stage does not need to produce one output for every input.
- A pipeline can have repeats of the same stages, with the exceptions of $out, $merge, and $geoNear. (all stages available [here]((https://docs.mongodb.com/manual/reference/operator/aggregation-pipeline/#aggregation-pipeline-operator-reference)))

### Example Pipline
```js
db.orders.aggregate([
    // finds instances in the database where the status is 'A'
   { $match: { status: "A" } },
   // groups them together as objects.
   { $group: { _id: "$cust_id", total: { $sum: "$amount" } } }
])
```

- The command 'aggregate' works over the ENTIRE mongo collection. Avoid this by using the following: $match, $sort, $group. 
- $match filters documents at the if it occurs at the beginning.
- $sort can use indexes as long as it is not preceded by a $project, $unwind, or $group.
- $group is preceded by a $sort stage that sorts the fields.

- with $geoNear, it has to go first.

### Early Filtering
- Use $match, $limit, $skip.