# Callbacks

A callback is a function you pass to be run later, when the result is ready.

You already saw that in the `setTimeout` example,
the arrow function was a callback that got called when the delay expired.

```javascript
const callback = (data) => {
  console.log('Data is ready!', data)
}

setTimeout(() => {
  callback('{some data}')
}, 1000) // 1000ms = 1s
```

> **Best Practice**
>
> Commonly, an "error first" callback pattern is used.
> 
> The first argument is the error (or null if no error), and the second argument is the result.
>
> ```javascript
> const callback = (error, result) => {
>   if (error) {
>     // something went wrong
>     console.error(error)
>   } else {
>     // we got the result
>     console.log(result)
>   }
> }
> ```