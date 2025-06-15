# Objects

* Objects store data as key-value pairs.
* Keys are called "properties".
* Values can be anything, like functions, or even nested objects!

## Object Literals

```javascript
const person = {
  name: 'Tom',
  age: 27,
  isMale: true,
}
```

Note: The curly braces `{}` denote an object here, not a code block.

## Dot Notation

Adding properties

```javascript
person.lastName = 'O\'Kane'
```

Accessing Properties

```javascript
console.log(person.age) // 27
```

## Bracket Notation

Adding properties

```javascript
person['lastName'] = 'O\'Kane'
```

Accessing Properties

```javascript
console.log(person['age']) // 27
```

Useful for dynamic keys.

```javascript
const key = 'age'
console.log(person[key]) // 27
```

## Deleting Properties

```javascript
delete person.lastName
```

## Nested Properties

```javascript
const user = {
  username: 'tom',
  address: {
    city: 'Shrewsbury',
    postcode: 'AB12 3CD'
  }
}

console.log(user.address.city) // "Shresbury"
```

---

# Common Object Methods

## Object.keys()

Get an array of object keys.

```javascript
const obj = { a: 1, b: 2, c: 3 }
console.log(Object.keys(obj)) /// ["a", "b", "c"]
```

## Object.values()

Get an array of object values.

```javascript
const obj = { a: 1, b: 2, c: 3 }
console.log(Object.values(obj)) /// [1, 2, 3]
```

## Object.entries()

Get an array of [key, value] pairs.

```javascript
const obj = { a: 1, b: 2, c: 3 }
console.log(Object.entries(obj)) /// [ ["a",1], ["b",2], ["c",3] ]
```

---

# Object Equality

Object variables are Reference Types:
The variable stores the _reference_ to the data, not the _data_ itself.

Equality therefore checks if the _reference_ is the same!

```javascript
const obj1 = { key: 'value' } // ref: 1
const obj2 = { key: 'value' } // ref: 2
const obj3 = obj1
console.log(obj1 === obj2) // false --> The reference is different (two objects)
console.log(obj1 === obj3) // true  --> The reference is the same (passed between them)
```

---

Under the hood, many things in JavaScript are objects:

* Arrays are objects with integer-like keys and extra array methods (e.g., push, pop).
* Strings are primitive values, but when accessed like objects (e.g., str[0] or str.length), JavaScript wraps them in
  String objects temporarily.
* Functions are first-class objects with a callable internal [[Call]] method and properties like `.name` and `.length`.
* Even other built-in types like Date, RegExp, and Error are objects.
* Primitives (string, number, boolean, null, undefined, symbol, bigint) are not objects, but some have object wrappers (
  e.g., String, Number).
