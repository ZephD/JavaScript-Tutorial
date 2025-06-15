# Number

```javascript
const myInt = 123
const myFloat = 123.456
const myExp = 1.2e3
```

---

# Useful Number Methods

## `.toFixed()`

Rounds the number to the fixed number of decimal places.

```javascript
const myNumber = 123.456
console.log(myNumber.toFixed(2)) // 123.45
```

Note this is called on the number variable.

## `.isFinite()`

Checks if the number is real. Returns a boolean.

```javascript
console.log(Number.isFinite(123))      // true
console.log(Number.isFinite(123.456))  // true
console.log(Number.isFinite('123'))    // false (string)
console.log(Number.isFinite(Infinite)) // false (infinite)
```

Note this uses the Number object.

## `.isInteger()`

Checks if the number is an integer. Returns a boolean.

```javascript
console.log(Number.isInteger(123))     // true
console.log(Number.isInteger(123.456)) // false
```

Note this uses the Number object.

## `.parseInt()`, `.parseFloat()`

Convert strings to numbers. Useful when reading numeric input from text.

```javascript
console.log(Number.parseInt('123'))       // 123
console.log(Number.parseInt('123px'))     // 123 (stops at non-digit)
console.log(Number.parseFloat('1.23'))    // 1.23
console.log(Number.parseFloat('1.23abc')) // 1.23
```

---

# Math

Javascript has a built in Math object, with many useful math methods to use with numbers.

* `Math.abs()` – absolute value
* `Math.round()` – round to nearest integer
* `Math.floor()` / `Math.ceil()` – round down / up
* `Math.max()` / `Math.min()` – largest / smallest value
* `Math.random()` – random number between 0 (inclusive) and 1 (exclusive)