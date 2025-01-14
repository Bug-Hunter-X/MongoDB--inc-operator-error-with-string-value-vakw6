# MongoDB $inc Operator Error with String Value

This repository demonstrates a common error when using the `$inc` operator in MongoDB updates. The error occurs when providing a string value instead of a numerical value to increment the field.

## Bug Description

The `$inc` operator in MongoDB is used to increment a numerical field by a specified value.  However, if a string value is used instead of a numerical value, it will result in an error and the update operation will fail.

## Bug Reproduction

1. Create a MongoDB collection named `myCollection` with a document that includes a `count` field.
2. Run the following MongoDB update operation:
   ```javascript
   db.collection('myCollection').updateOne({ _id: 1 }, { $inc: { count: '1' } });
   ```
3. Observe the error that occurs.

## Solution

The solution is to ensure that the value provided to the `$inc` operator is a valid number.  The following example demonstrates the correct usage of `$inc`:

```javascript
   db.collection('myCollection').updateOne({ _id: 1 }, { $inc: { count: 1 } });
   ```