# For Loop

Often we want to iterate a known number of times.

```javascript
let i = 0

while (i < 10) {
  console.log(i)
  i++
}
```

However, the `i` variable is only used for the `while` loop, but is assigned globally.

A `for` loop combines the **initialisation**, the **conditional** check, and the **update** step in a concise way, bound to it's own scope.

```javascript
for (let i = 0; i < 10; i++) {
  console.log(i);
}
```

## Break Statement

Like `while` loops, a `break` statement can be used to immediately exit the loop, stopping further iterations.

## Continue Statement

Like `while` loops, a `continue` statement can be used to immediately skip the remaining loop, starting the next one.

## For-Of

Used to iterate over the **values** of an iterable (like arrays, strings, etc.).

```javascript
const array = [1, 2, 3]

for (const value of array) {
  console.log(value) // 1, 2, 3
}
````

## For-In

Iterate over the **keys** of an object (or array).

```javascript
const obj = { a: 1, b: 2 }

for (const key in obj) {
  console.log(key) // "a", "b"
}
```

