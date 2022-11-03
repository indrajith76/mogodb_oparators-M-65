## What are MongoDB operators?
- MongoDB offers different types of operators that can be used to interact with the database.
- Operators are special symbols or keywords that inform a compiler or an interpreter to carry out mathematical or logical operations.
- The query operators enhance the functionality of MongoDB by allowing developers to create complex queries to interact with data sets that match their applications.
- MongoDB offers the following query operator types:<br>
i. Comparison<br>
ii. Logical<br>
iii. Element<br>
iv. Evaluation<br>
V. Geospatial<br>
vi. Array<br>
vii. Bitwise<br>
viii. Comments<br>

## Comparison Operators
MongoDB comparison operators can be used to compare values in a document. The following table contains the common comparison operators.
|Operator|Description|
|---|---|
|$eq|Matches values that are equal to the given value.|
|$gt|Matches if values are greater than the given value.|
|$It|Matches if values are less than the given value.|
|$gte|Matches if values are greater or equal to the given value.|
|$ite|Matches if values are less or equal to the given value.|
|$in|Matches any of the values in an array.|
|$ne|Matches values that are not equal to the given value.|
|$nin|Matches none of the values specified in an array.|

### Comparison Operators ($eq)
In this example, we retrieve the document with the exact qty value 20.
> Syntax: {field: ($eq: value}}

```js
Input:
db.inventory.find({ qty: { $eq: 20 } })```

```js
Output:
fid: 2, item: { name: "cd", code: "123" }, qty: 28, tags: [ "B" ] } (id: 5, item: { name: "mn", code: "000" }, qty: 20, tags: II "A", "B" 1, "C" 1 }
```