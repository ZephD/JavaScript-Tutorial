# Promise

The Javascript **Promise** is one way to handle asynchronous code.

It represents a value that’s not ready yet, but will be later.

The Promise take a function that has two callbacks:
one to call to `resolve` the promise on success,
and one to call to `reject` the promise on failure.

```javascript
// Create a promise (started immediately)
const promise = new Promise((resolve, reject) => {
  const result = doSomethingSlow()
  if (result.error) return reject('Oops, error!')
  if (result.data) return resolve('Yay, data!')
})

promise
  .then(result => {
    // Called if resolved
    console.log(result) // "Yay, data!"
  })
  .catch(error => {
    // Called if rejected
    console.error(error) // "Oops, error!"
  })
  .finally(() => {
    // Always runs, after previous handelrs
    console.log('Done!')
  })
```

Notice how it's quite similar to `try`-`catch`-`finally`?

## Promise.resolve()

Creates a promise that immediately resolves with the given value.

```javascript
Promise.resolve('Hello')
  .then(data => {
    console.log(data) // "Hello"
  })
```

## Promise.all()

Takes an array of promises that:

* **Resolves** when **all** promises finish successfully
* **Rejects** if **any** promise fails.

```javascript
const p1 = Promise.resolve('A')
const p2 = Promise.resolve('B')
const p3 = Promise.resolve('C')

// All 3 promises start at the same time (not synchronously).
Promise.all([p1, p2, p3])
  .then(results => {
    console.log(results) // ['A', 'B', 'C']
  })
```

```javascript
const p1 = Promise.resolve('A')
const p2 = Promise.reject('Oops!')
const p3 = Promise.resolve('C')

Promise.all([p1, p2, p3])
  .then(results => {
    // skipped
  })
  .catch(error => {
    console.error(error) // "Oops!"
  })
```

## Chaining

You can chain, and mix-and-match, multiple promise handlers.

Each `.then()` gets the value **returned** by the previous handler.

Thrown errors skip to the next `.catch()` handler.

```javascript
Promise.resolve("my data") // A promise that immedaitely calls resolve.
  .then(data => {
    console.log(data) // "my data"
    return "new data"
  })
  .then(data => {
    console.log(data) // "new data"
    throw new Error('Oops') // Jumps to the next .catch()
  })
  .then((data) => {
    console.log(data) // Does not get called due to error skipping this .then()
  })
  .catch(error => {
    console.error(error) // "Oops"
    return "error handeled"
  })
  .then(data => {
    console.log(data) // "error handeled"
  })
  .finally(data => {
    console.log('All done!')
    return 'done'
  })
  .then(data => {
    console.log(data) // "done"
  })
```
