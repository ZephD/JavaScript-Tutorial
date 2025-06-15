# Arithmetic Operators

## Plus: `+`

```javascript
console.log(1 + 1)                       // 2
console.log(123.456 + 765.432 + 456.543) // 1345.431
```

## Minus: `-`

```javascript
console.log(7 - 5)     // 2
console.log(5 - 7 - 3) // -5
```

## Multiply: `*` (asterisk)

```javascript
console.log(7 * 3)     // 21
console.log(7 * 3 * 8) // 168
```

## Divide: `/` (forward-slash)

```javascript
console.log(20 / 2) // 10
console.log(17 / 3) // 5.66666...
console.log(1 / 0)  // Infinity
```

## Exponent: `**`

```javascript
console.log(3 ** 2) // 9 (= 3*3)
console.log(2 ** 3) // 8 (= 2*2*2)
```

## Modulus/Remainder: `%`

```javascript
console.log(8 % 3) // 2
```

"I have 8 apples and 3 customers.
I give them as many whole apples as I can, and the same amount, each.
How many do I have left?"

Often used for an Even/Odd check:

```javascript
console.log(1 % 2) // 1
console.log(2 % 2) // 0
console.log(3 % 2) // 1
console.log(4 % 2) // 0
```

## Increment (plus one): `++`

Requires the use of `let` as it re-assigns the number.

```javascript
let x = 5
console.log(x)    // 5
const y = x++     // Returns value, THEN increments
console.log(x, y) // 6, 5
const z = ++x     // Increments, THEN returns value
console.log(x, z) // 7, 7
```

## Decrement (minus one): `--`

```javascript
let counter = 2
console.log(--counter) // 1
```
