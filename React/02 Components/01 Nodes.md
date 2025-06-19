# Components

React components are JavaScript **functions** that return a UI element (a "React Node") written in JSX.

JSX stands for **J**ava**s**cript **X**ML, which has HTML-like syntax.

```javascript
const MyComponent = (props) => {

  /* Setup code goes here */

  return (
    /* Renderable (jsx) code goes here */
    <h1>Hello World</h1>
  )
}

export default MyComponent
```

## React Nodes

React Nodes can be:

* Built-in (HTML) components (`<div>`, `<p>`, `<button>`, etc.).
* Custom Components (e.g. `<MyComponent>`).
* Strings (i.e. `Hello`)
* Numbers (i.e. `123`)
* boolean, null, undefined (ignored)

## Dynamic Content

You can embed a JavaScript **expression** into JSX using `{}` notation.

This allows for dynamic content.

(It is _not_ a code block, and cannot contain `if`, `for`, etc.)

```javascript
const Greet = () => {
  const name = 'Alice'
  return (
    <h1>Hello {name}</h1>
  )
}
```
