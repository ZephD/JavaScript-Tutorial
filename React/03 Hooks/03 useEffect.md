# [useEffect](https://react.dev/reference/react/useEffect)

`useEffect` is a hook that lets you update your component with _external systems_.

It takes two arguments:

1. The setup function
2. An array of dependencies the function relies on.

If React detects a change in a dependency, it will re-run the setup function.

If the dependency array is empty, the setup function will only run **once**, when the Component first mounts.

## Fetching Data

A easy example of "external state" is fetching data from the internet.

```javascript
import { useState, useEffect } from 'react'

const MyComponent = ({ url }) => {
  const [data, setData] = useState(null)

  useEffect(() => {
    fetch(url)
      .then(result => result.text())
      .then(text => setData(text))
  }, [url]) // Re-run if URL changes.

  return (
    <div>{data}</div>
  )
}
```

Here, the `url` comes from the parent component as a prop.  
Initially, our `data` state is `null`, so an empty `<div>` is rendered.
`useEffect` runs once initially (on mount), and we fetch the data,
and (when ready) save the output into a `useState` variable.  
This causes a re-render, displaying the new data.

If the `url` changes in the parent (say, upon user input),
since we watch the `url` in our dependency array,
we re-run the effect code, updating it with the data from the new `url` fetch.

> **Best Practise**
>
> The dependency array should contain all (primitive) props/state
> that are **used** within the setup function.

## Initialising Components

`useEffect` can also be used, with an empty dependency array,
to initialise some component setup on mount.

```javascript
import { useEffect, useRef } from 'react'

const NameForm = () => {
  const inputRef = useRef()

  useEffect(() => {
    inputRef.current.focus() // Focus the input
  }, []) // Run once, on mount.

  return (
    <input
      ref={inputRef}
      type="text"
      placeholder="Enter your name"
    />
  )
}
```

## Cleanup Function

The `useEffect` setup function can return a cleanup function.

This function gets run just before the component **unmounts**
(e.g. when the user navigates away from the page),
and before the setup function **runs again** (e.g. on dependency change).

This can be useful to cancel an async request, or clear an interval before setting up a new one.

```javascript
import { useState, useEffect } from 'react'

const AdjustableTimer = () => {
  const [count, setCount] = useState(0)
  const [delay, setDelay] = useState(1000)

  useEffect(() => {
    const id = setInterval(() => setCount(c => c + 1), delay)
    return () => clearInterval(id) // clear old interval before starting a new one
  }, [delay]) // run again when delay changes

  return (
    <div>
      <div>Seconds: {count}</div>
      <button onClick={() => setDelay(500)}>Faster (500ms)</button>
      <button onClick={() => setDelay(1000)}>Normal (1000ms)</button>
      <button onClick={() => setDelay(2000)}>Slower (2000ms)</button>
    </div>
  )
}
```