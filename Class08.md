# Class 08 Reading
## Populate-
Process of automatically replacing the specified paths in the document with documents from other collections. 
```js
const mongoose = require('mongoose');
const Schema = mongoose.Schema;

// In the personSchema, _id needs an object id. Stories is an array of object ids referencing the Story mongoose model. Equivalent to foreign key in SQL.
const personSchema = Schema({
  _id: Schema.Types.ObjectId,
  name: String,
  age: Number,
  stories: [{ type: Schema.Types.ObjectId, ref: 'Story' }]
});

const storySchema = Schema({
  author: { type: Schema.Types.ObjectId, ref: 'Person' },
  title: String,
  fans: [{ type: Schema.Types.ObjectId, ref: 'Person' }]
});

const Story = mongoose.model('Story', storySchema);
const Person = mongoose.model('Person', personSchema);
```



## Populate Virtuals
Allows for matching between documents not based solely on id.
```js
const PersonSchema = new Schema({
  name: String,
  band: String
});

const BandSchema = new Schema({
  name: String
});
BandSchema.virtual('members', {
  ref: 'Person', // The model to use
  localField: 'name', // Find people where `localField`
  foreignField: 'band', // is equal to `foreignField`
  // If `justOne` is true, 'members' will be a single doc as opposed to
  // an array. `justOne` is false by default.
  justOne: false,
  options: { sort: { name: -1 }, limit: 5 } // Query options, see http://bit.ly/mongoose-query-options
});

const Person = mongoose.model('Person', PersonSchema);
const Band = mongoose.model('Band', BandSchema);

/**
 * Suppose you have 2 bands: "Guns N' Roses" and "Motley Crue"
 * And 4 people: "Axl Rose" and "Slash" with "Guns N' Roses", and
 * "Vince Neil" and "Nikki Sixx" with "Motley Crue"
 */
Band.find({}).populate('members').exec(function(error, bands) {
  /* `bands.members` is now an array of instances of `Person` */
});
You can also use the populate match option to add an additional filter to the populate() query. This is useful if you need to split up populate() data:

const PersonSchema = new Schema({
  name: String,
  band: String,
  isActive: Boolean
});

const BandSchema = new Schema({
  name: String
});
BandSchema.virtual('activeMembers', {
  ref: 'Person',
  localField: 'name',
  foreignField: 'band',
  justOne: false,
  match: { isActive: true }
});
BandSchema.virtual('formerMembers', {
  ref: 'Person',
  localField: 'name',
  foreignField: 'band',
  justOne: false,
  match: { isActive: false }
});
```