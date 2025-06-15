# Pure Functions

> **Best Practice**
>
> Functions should be "pure":
> * Always returns the **same output** for the **same inputs**.
> * Has no side effects (e.g., no external mutation, including console.log)

Pure Example:

```javascript
const add = (a, b) => a + b
```

* Given the same `a` and `b`, always returns the same result.
* Does not change anything outside of the function.

```javascript
let counter = 0

const increment = () => {
  counter++
  console.log(counter)
  return counter
}
```

* Depends on external state.
* Modifies external state.
* Calling it multiple times changes the output.
* Logs to console.

## Why pure?

* Easier to debug.
* More predictable and reliable.
