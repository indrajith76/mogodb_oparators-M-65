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

<hr>

## Comparison Operators ($eq) :
In this example, we retrieve the document with the exact qty value 20.<br>
### Syntax: {field: ($eq: value}}

```js
Input:
db.inventory.find({ qty: { $eq: 20 } })
```

<br>

```js
Output:
{_id: 2, item: { name: "cd", code: "123" }, qty: 28, tags: [ "B" ] } 
{_id: 5, item: { name: "mn", code: "000" }, qty: 20, tags: ["A"], "B" 1, "C" 1 }

```

## Comparison Operators ($gt):
In this example, we retrieve the documents where the quantity is greater than 20.
### Syntax: {field: {$gt: value}}
```js
Input:
db.inventory.find({ quantity: {$gt: 20 } })
```
```js
Output:
{
    _id: ObjectId("61ba25cbfe687fce2f842414"), 
    item: 'nuts', 
    quantity: 30, 
    carrier: { name: 'Shipit', fee: 3 }
},
{
    _id: ObjectId("61ba25cbfe687fce2f842415"), 
    item: 'bolts', 
    quantity: 50, 
    carrier: { name: 'Shipit', fee: 4 } 
} 
```

## Comparison Operators ($gte):
In this example, we retrieve the documents where the quantity is greater than or equal to 20.<br>
### Syntax: {field: {$gte: value}}
```js
Input:
db.inventory.find({ quantity: {$gte: 20 } })
```

```js
{
    _id: ObjectId("61bb51211b83c864e3bbe037"), item: 'nuts', 
    quantity: 30, 
    carrier: { name: 'Shipit', fee: 3 }
},
{
    _id: ObjectId("61bb51211b83c864e3bbe038"), item: 'bolts',
    quantity: 20, 
    carrier: { name: 'Shipit', fee: 4 } 
}
```

## Comparison Operators ($It):
In this example, we retrieve the documents where the quantity is less than 20.<br>
### Syntax: {field: {$lt: value}}
```js
Input:
db.inventory.find({ quantity: { $lt: 20 } })
```
```js
Output:
{
    id: ObjectId("61ba634dfe687fce2f04241f"), item: 'washer',
    quantity: 10,
    carrier: { name: 'Shipit', fee: 1 }
}
```

## Comparison Operators ($Ite):
In this example, we retrieve the documents where the quantity is less than or equal to 20.<br>
### Syntax: {field: {$lte: value}}
```js
Input:
db.inventory.find( { quantity: { $lte: 20 } })
```
```js
Output:
{
    id: ObjectId("61ba453ffe687fce2f04241b"), item: 'bolts', 
    quantity: 20, 
    carrier: { name: 'Shipit', fee: 1 }
}
{
    _id: ObjectId("olba453ffe687fce2f04241c"), item: 'washers', 
    quantity: 10, 
    carrier: { name: 'Shipit', fee: 4 }
}
```

## Comparison Operators ($in):
In this example, we retrieve the documents where the quantity contains the given values.<br>
### Syntax: field: { $in: [< value >, < value2 >, ... < valueN > ] } }
```js
Input:
db.inventory.find({ quantity: { $in: [ 5, 15 ] } }, { id: 0 })
```
```js
Output:
{ item: 'Erasers', quantity: 15, tags: [ 'school', 'home' ] }, 
{ item: 'Books', quantity: 5, tags: [ 'school', 'storage', 'home' ] }
```

## Comparison Operators ($nin)
In this example, we retrieve the documents where the quantity do not contain the given values.<br>
### Syntax: field: { $nin: [ < value >, < value2 > ... < valueN > ] } }
```js
Input:
db.inventory.find( {quantity: { $nin: [ 5, 15 ] } }, { id: @})
```
```js
Output:
{ item: 'Pens', quantity: 350, tags: ['school', 'office'] }, 
{ item: 'Maps', tags: ['office', 'storage' ]}
```

## Comparison Operators ($ne)
In this example, we retrieve the documents where the quantity is not equal to the given values.<br>
### Syntax: { field: { $ne: value } }
```js
Input:
db.inventory.find({ quantity: { $ne: 20 } })
```
```js
Output:
{
    _id: ObjectId("61ba667dfe687fce2f042420"), item: 'nuts', 
    quantity: 30, 
    carrier: { name: 'Shipit', fee: 3 }
},
{
    _id: ObjectId("61ba667dfe687fce2f042421"), item: 'bolts', 
    quantity: 58, 
    carrier: { name: 'Shipit', fee: 4 }
},
{
    _id: ObjectId("61ba667dfe687fce2f042422"), item: 'washers', 
    quantity: 10, 
    carrier: { name: 'Shipit', fee: 1 }
}
```