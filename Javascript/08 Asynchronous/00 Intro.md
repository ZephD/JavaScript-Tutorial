# Asynchronous code

So far, our code runs **top to bottom**, in order.

But some things can take _time_, like fetching data from the internet.

It would be bad for yor application to just stop everything and wait!

Instead, JavaScript can start the task, then continue going.
Once the things is ready, it can _then_ action it.

This is called **asynchronous** behaviour.

# setTimeout()

One way to delay actions (or to mock asynchronous code) is the `setTimeout` function.

`setTimeout` takes a function to call (first param) after a given delay (second param) in ms.

```javascript
console.log('This log happens first.')
setTimeout(() => {
  console.log('This log happens third - after one second.')
}, 1000) // 1000ms = 1s
console.log('This log happens second.')
```

The `setTimeout` is created as normal (after the first message) in a script like fashion,
and is setup to run the given function after a delay.

Once set up, the rest of the script continues (logging the second message).

After the delay, the provided function is run (logging the third message).

> **Further Reading**: The Event Loop
> 
> Behind the scenes, JavaScript uses something called the **Event Loop** to keep track of delayed tasks and run them when
ready.