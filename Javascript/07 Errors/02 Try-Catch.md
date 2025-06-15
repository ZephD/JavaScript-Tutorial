# Try-Catch

Sometimes, errors are expected, and need to be handled to prevent your code from stopping.

This is done with a try-catch statement.

```javascript
try {
  // The code that may throw an error
} catch (error) {
  // Code to handle the error, like inform the user
  console.error(error)
}
```

## Finally

Sometimes, you want to run code regardless of whether the code succeeded or threw an error.

You can do this with the `finally` statement after `catch`.

```javascript
try {
  // The code that may throw an error
} catch (error) {
  // Code to handle the error
} finally {
  // Code to perform cleanup, runs always
}
```