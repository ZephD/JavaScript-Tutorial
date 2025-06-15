# Async/Await

`async` and `await` make working with promises easier.

They let you write async code that looks like regular code.

Asynchronous functions (that contain asynchronous calls) can be marked with `async`.

Asynchronous calls inside this function can then be `await`ed to wait until the result is ready.

```javascript
const asyncFunc = () => new Promise(resolve => {
  setTimeout(() => {
    resolve("Hello!")
  }, 1000)
})

const doAsync = async () => {
  console.log('B')
  const result = await asyncFunc() // Wait for the response
  console.log(result)              // Logs once the delay is over
  console.log('D')
}

console.log('A')
doAsync() // Call the async function
console.log('C')
```

## Try-Catch

You can use `try`-`catch` to handle errors with `await`ed calls.

```javascript
const doAsync = async () => {
  try {
    const data = await someAsyncTask()
    console.log('Success:', data)
  } catch (error) {
    console.error('Error:', error)
  }
}

```