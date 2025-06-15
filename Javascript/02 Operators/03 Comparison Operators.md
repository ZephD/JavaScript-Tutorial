# Comparision Operators

All Comparison operators return a Boolean (true or false)

## Equal to: `===`
```javascript
console.log(5 === 4) // false
console.log(5 === 5) // true
console.log(5 === 6) // false
```

## Not Equal to: `!==`
```javascript
console.log(5 !== 4) // true
console.log(5 !== 5) // false
console.log(5 !== 6) // true
```

## Greater than: `>`
```javascript
console.log(5 > 4) // true
console.log(5 > 5) // false
console.log(5 > 6) // false
```

## Greater than or equal to: `>=`
```javascript
console.log(5 >= 4) // true
console.log(5 >= 5) // true
console.log(5 >= 6) // false
```

## Less than: `<`
```javascript
console.log(5 < 4) // false
console.log(5 < 5) // false
console.log(5 < 6) // true
```

## Less than or equal to: `<=`
```javascript
console.log(5 <= 4) // false
console.log(5 <= 5) // true
console.log(5 <= 6) // true
```

---

# Abstract Equality

Javascript actually has a "loose" and "strict" comparators

## "Abstract" Equality: `==` or `!=`
Performs type conversion
```javascript
console.log(1 == 1)    // true
console.log(1 == '1')  // true
console.log(1 == true) // true
```

## "Strict" Equality: `===` or `!==`
Additionally checks for type equality
```javascript
console.log(1 === 1)    // true
console.log(1 === '1')  // false
console.log(1 === true) // false
```

> **Best Practice**
> 
> Always use strict equality (`===`).
---

# Truthy-ness

Javascript has "Truthy" and "Falsy" values

The following are considered "Falsy":
* `false`
* `0` (zero)
* `''` or `""` (empty string)
* `null`
* `undefined`
* `NaN`

_Everything_ else is "Truthy".
Including:
* All non-zero numbers
* All non-empty strings, e.g. `'false'`, `'0'`
* All Objects `{}`, even if empty
* All Arrays `[]`, even if empty
