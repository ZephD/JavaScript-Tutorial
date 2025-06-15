# While Loop

Sometimes we want to run a bit of code many times.

"While (the condition is true) do { the following code }"

```javascript
let count = 0

while (count < 10) {
  // Ooh, another code block! Local scope!
  console.log(count++)
}
```

## Break Statement

A `break` statement can be used to immediately exit the loop, stopping further iterations.

```javascript
let count = 0

while (true) { // Possible infinite loop!
  count++
  if (count > 10) {
    break // Exit the loop
  }
}

console.log(count) // 11
```

> **Best Practice**
>
> `while (true)` will run indefinitely, locking up the programme, unless you `break` out of it.
>
> Avoid using this, or use it with caution.

## Continue Statement

A `continue` statement can be used to immediately skip the remaining loop, starting the next one.

```javascript
const count = 0

while (count < 10) {
  count++
  if (count < 5) {
    continue // Skip the rest of the loop
  }
  console.log(count) // 5, 6, 7 ...
}
```

## Do-While

Sometimes we want to execute the code block once before checking the conditional.

We can use a `do`-`while` loop for this.

```javascript
let count = 0

do {
  console.log('Count is:', count)
  count++
} while (count < 10)
```

If `count` started above `10`, it'll skip logging anything.
Do while makes sure we get at least one log.