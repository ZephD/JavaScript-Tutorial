# Destructuring

Javascript allows you to unpack an object or array into variables.

## Object Destructuring

```javascript
const obj = { a: 1, b: 2, c: 3 }

const { a, c } = obj

console.log(a) // 1
```

Useful for extracting only necessary properties from an object.

Can also be used for function parameters. (Used extensively for props in React components.)

```javascript
const person = { name: 'Tom', age: 27 }

const greet = ({ name }) => `Hello ${name}`

console.log(greet(person))
```

## Array Destructuring

```javascript
const array = [1, 2, 3, 4]

const [first, second] = array

console.log(first) // 1
```

Useful for functions that need to return multiple items.

The user can set the names of the returned items. (This is used extensively in React Hooks.)

```javascript
const useState = (initial) => {
  let value = initial
  const setFunc = newValue => value = newValue
  return [value, setFunc]
}

const [count, setCount] = useState(0)
```