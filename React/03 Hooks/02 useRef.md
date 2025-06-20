# [useRef](https://react.dev/reference/react/useRef)

But what if you want to hold state that _does **not**_ affect the UI?  
This is where `useRef` can help.

(**Note**: You're unlikely to need this Hook early on).

`useRef` returns and object that has a `current` property (i.e. `{ current }`).  
You can directly mutate the `current` property to update the state.  
Since the object does not change (it's reference does not change),
no re-render is triggered.

```javascript
const myRef = useRef(0)
myRef.current += 1
```

> **Best Practise**
>
> Do not read or write to `current` within the render (JSX) code, as it won't update.  
> You should use `useState` for UI variables, which triggers renders on detected changes.  
> Refs are often changed at the top of the component or within event handlers (e.g. button clicks).

An example is keeping track of a timeoutId.  
Since changing a timeoutId has no impact on the UI,
we don't want to use `useState` to track this variable,
which would re-render the component every click!.

```javascript
const MyComponent = () => {
  const timeoutRef = useRef(null)
  
  const handleClick = () => {
    clearTimeout(timeoutRef.current)
    
    timeoutRef.current = setTimeout(() => {
      console.log('Boo!')
    }, 3000)
  }
  
  return (
    <button onClick={handleClick}>
      Click Me Rapidly!
    </button>
  )
}
```

Here, the timeout is cleared each time the button is pressed,
so only the last click (after 3 seconds) creates the log,
rather than each click.

## DOM Refs

`useRef`'s primary use is for getting the DOM element of a component.

You can then access DOM features (like `width` or `height`) and functions (like `.focus()`, `.select()`, etc.) 

```javascript
import { useRef } from 'react'

const VideoPlayer = () => {
  const videoRef = useRef()

  const handlePlay = () => videoRef.current.play()
  const handlePause = () => videoRef.current.pause()

  return (
    <div>
      <video
        ref={videoRef} // <-- Here!
        src="https://www.w3schools.com/html/mov_bbb.mp4"
        width="320"
        controls={false}
      />
      <div>
        <button onClick={handlePlay}>Play</button>
        <button onClick={handlePause}>Pause</button>
      </div>
    </div>
  )
}

```
