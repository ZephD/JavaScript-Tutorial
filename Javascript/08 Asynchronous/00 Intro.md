# Asynchronous code

So far, our code runs **top to bottom**, in order.

But some things can take _time_, like fetching data from the internet.

It would be bad for yor application to just stop everything and wait!

Instead, JavaScript can start the task, then continue going.
Once the things is ready, it can _then_ action it.

This is called **asynchronous** behaviour.

> **Further Reading**: [The Event Loop](https://www.youtube.com/watch?v=eiC58R16hb8)
>
> Behind the scenes, JavaScript uses something called the **Event Loop**
> to keep track of asynchronous tasks and runs them when JS is idle.

## setTimeout()

One way to delay actions (or to mock asynchronous code) is the `setTimeout` function.

`setTimeout` takes a function to call (first param) after a given delay (second param) in ms.

```javascript
console.log('This log happens first.')
const timeoutId = setTimeout(() => {
  console.log('This log happens third - after one second.')
}, 1000) // 1000ms = 1s
console.log('This log happens second.')

clearTimeout(timeoutId) // This will cancel the timeout, if called before it triggers.
```

The `setTimeout` is created as normal (after the first message) in a script like fashion,
and is setup to run the given function after a delay.

Once set up, the rest of the script continues (logging the second message).

After the delay, the provided function is run (logging the third message).  
(Assuming it's not cleared like in the example above. Comment it out to see this.)

## setInterval()

A similar function to setTimeout, but this sets up a function to run repeatedly.

```javascript
const intervalId = setInterval(() => {
  console.log('Hello!')
}, 1000) // 1000ms = 1s

clearInterval(intervalId) // This will stop the interval.
```

This will log "Hello!" every second, until cleared.