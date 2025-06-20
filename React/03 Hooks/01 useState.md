# [useState](https://react.dev/reference/react/useState)

Probably the most used React Hook.

`useState` is used to store data that affects the UI:
if React detects a change in the state,
it triggers the component to re-render,
so the UI refreshes and stays up to date.

You import hooks as named imports from `react`.

```javascript
import { useState } from 'react'
````

It takes an **initial state** as an argument.  
It returns an array of arguments, that is often destructured:

* The first element is the **state** (data).
* The second element is the **setter function**.

It uses array destructuring so you can set your own variable names.

```javascript
const [state, setState] = useState(initialState)
```

You create Hooks at the top of your component.

Example counter:

```javascript
import { useState } from 'react'

const Counter = () => {
  // Use hooks at the top of your component.
  const [count, setCount] = useState(0) // Initial Value: 0
  
  const handleButtonClick = () => setCount(count + 1)

  return (
    <button onClick={handleButtonClick}>
      You clicked {count} times
    </button>
  )
}
```

## setState(() => {})

What if we tried:

```javascript
const handleClick = () => {
  setCount(count + 1)
  setCount(count + 1)
  setCount(count + 1)
}
```

What do you expect the value to be afterwards? You'd expect it to be 3 larger.

However, the value of `count` does not update immediately after each call,
only after the whole action (handleClick) is processed and the component re-renders.

Therefore, if `count = 2`, you're simply saying `setCounter(2+1)` three times,
which is the same as saying `setCounter(3)` three times. So the result will be `3`.

To avoid this, the state setter (`setCount`) **can take a function**, which is provided with the latest state.

```javascript
const handleClick = () => {
  setCount(state => state + 1) // 2 => 2 + 1 (3)
  setCount(state => state + 1) // 3 => 3 + 1 (4)
  setCount(state => state + 1) // 4 => 4 + 1 (5)
}
```

The `state` in the function is updated each call for the next call, so this works as expected.

> **Best Practise**
>
> Always use the functional form, if your update logic depends on the current state.
