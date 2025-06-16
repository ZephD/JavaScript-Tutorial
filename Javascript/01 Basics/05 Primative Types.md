# Primitive Types

* Stored by **value**.
* Directly holds the **data**.
* **Immutable** (cannot be changed).

Assigning a primitive **copies the value**.

## Boolean

`true` or `false`

```javascript
const myBoolean = false
console.log(myBoolean)        // false
console.log(typeof myBoolean) // "boolean"
```

## Number

Numerical values.

```javascript
const myNumber = 123
console.log(myNumber)        // 123
console.log(typeof myNumber) // "number"
```

Integer (123) or Floating Point (1.23). JavaScript Doesn't care

## String

Text.

```javascript
const myString = 'Hello there!'
console.log(myString)        // "Hello there!"
console.log(typeof myString) // "string"
```
* Can use `'` (single) or `"` (double) quotes. (`'` is more common)
* Can also use `` ` ``  (backtick). More on that later.

## Undefined

A un-set variable (quite unique to Javascript)

```javascript
let myUndefined
console.log(myUndefined)        // undefined
console.log(typeof myUndefined) // "undefined"
```

## Symbol

... another time.

## Null

```javascript
const myNull = null
console.log(myNull)        // null
console.log(typeof myNull) // "object" (Legacy Reason)
```

### Null vs Undefined

- **Undefined**: A variable that has been **declared**, but not **assigned** a value.
- **Null**: A variable that has been **explicitly assigned** to "nothing".
    - Represents the **intentional absence** of any object value.
    - Conceptually similar to a "null pointer" — no reference in memory.