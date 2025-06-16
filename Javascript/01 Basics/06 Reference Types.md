# Reference Types

* Stored by **reference**.
* Points to the data, does not hold the data.
* **Mutable**, can be modified (e.g. adding a property/element).

## Object

Key-Value containers

```javascript
const myObject = { key: 'value' }
console.log(myObject)        // { key: "value" }
console.log(typeof myObject) // "object"
```

Values can be anything, like functions or even other (nested) objects!

## Array

Ordered Value Lists.

Arrays (in Javascript) are **zero-indexed** (the first item has an index `0`).

```javascript
//        Index:  0    1    2
const myArray = ['a', 'b', 'c']
console.log(myArray)        // ['a', 'b', 'c']
console.log(typeof myArray) // "object"
```

Values can be anything.

## Function

Re-usable blocks of code, with input(s) and an output.

```javascript
function myFunction(input) {
  /* code goes here */
  return "output"
}

console.log(myFunction)        // [Function: myFunction]
console.log(myFunction())      // "output" (the returned value, when called)
console.log(typeof myFunction) // "function"
```
Note this is has a code block - it's scoped! Variables defined in here stay in here.