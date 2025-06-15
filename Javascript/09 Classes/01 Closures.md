# Closures

A **closure** happens when a function remembers variables (state) from its outer scope.

```javascript
const createCounter = () => {
  let count = 0        // State
  return () => ++count // Returns a function
}

const counter = createCounter() // (0)
console.log(counter())          // 1
console.log(counter())          // 2
```

* `count` lives inside `crateCounter`.
* The returned function **remembers** the variable.
* The closure lets you keep **private state**