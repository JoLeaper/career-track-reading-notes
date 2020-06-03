# Class 03 Reading

Question 1. Why would a developer choose to make data models?

Answer: "A data model not only improves the conceptual quality of an application, it also lets you leverage database features that improve data quality." 

Referenced ( https://www.dataversity.net/data-models-many-benefits-10/#:~:text=A%20data%20model%20not%20only,normally%20have%20a%20primary%20key )

Question 2. What purpose do CRUD operations serve?

Answer: They create, read, update, and delete data from a database.

Question 3. What kind of database is Postgres? What kind of database is MongoDB?

Answer: Postgres is an object-relational database management system (ORDBMS). It is a heavily structured (or schema) database.

MongoDB is a schema-free database, meaning that data/structures can differe between documents.

Referenced (https://blog.panoply.io/postgresql-vs-mongodb#:~:text=PostgreSQL%20also%20supports%20many%20NoSQL,can%20vary%20for%20different%20documents.&text=This%20means%20that%20collections%20in%20MongoDB%20are%20like%20tables%20in%20RDBMS.)

Question 4. What is Mongoose and why do we need it?

Answer: Mongoose is a data library that better organizes MongoDB to make it more usable while retaining its flexibility.

Reference (https://devcenter.heroku.com/articles/nodejs-mongoose)

Question 5. Define three related pieces of data in a possible application. An example for a store application might be Product, Category and Department. Describe the constraints and rules on each piece of data and how you would relate these pieces to each other. For example, each Product has a Category and belongs in a Department.

Answer: Yu-Gi-Oh Cards Application. Cards, Packs, Cost. Cards have a one to many relationship with packs and costs (a card can appear in multiple packs, and a card can have multiple rarities to make its price vary). 

| Term   | Definition  |
|---|---|
| **database**  | An organzied collection of data.  |
| **data model**  | Abstract model that organizes elements and how they are related to each other. |
| **CRUD**  | Create, Read, Update, Delete (four basic data functions). |
| **schema**  | Organization of data (as it relates to how the database is destructed) |
| **sanitize**  | The removal of all dangerous characters before it gets passed to a SQL engine.  |
| **Structured Query Language**  | Programming language that uses operations to retrive information from relational databases. |
| **Non SQL(No SQL)**  | A database that uses data that is modeled in a non-table database. |
| **MongoDB**  | Cross-platform document-oriented database program.|
| **Mongoose**  | Mongoose is a data library that better organizes MongoDB to make it more usable while retaining its flexibility. |
| **record**  | object that can contain one or more values in a database. |
| **document**  | Superset of all other data models to allow for versatile data strcutring. |
| **Object Relation Mapping (ORM)**  | Technique used for converting data between incompatible type systems. |