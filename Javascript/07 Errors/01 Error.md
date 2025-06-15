# Errors

An error happens when something goes wrong in your code.

A unhandled error will stop the programme from running.

## Compile-Time Errors

These happen before your code runs.

Your IDE will usually catch these and tell you.

```javascript
const b =  // SyntaxError: unexpected end of input
```

## Run-Time Errors
These happen while you code it running.

Often due to unexpected data or unhandled cases.

```javascript
console.log(notDefined)   // ReferenceError: notDefined is not defined

null.toUpperCase()        // TypeError: Cannot read property 'toUpperCase' of null

const arr = new Array(-1) // RangeError: Invalid array length
```

## Custom Errors

You can create an error and give it a message and throw your own custom errors.

You `throw` an error (similar to `return`, but for errors).

```javascript
const value = 3
if (value < 5) {
  const error = new Error('The value is too small!')
  throw error
}
```
