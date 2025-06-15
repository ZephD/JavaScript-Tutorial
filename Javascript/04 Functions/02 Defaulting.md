# Defaulting Parameters

Parameters can be given default values.

```javascript
const greet = (name = 'Guest') => 'Hello' + ' ' + name

console.log(greet())      // "Hello Guest"
console.log(greet('Tom')) // "Hello Tom"
```

> **Best Practice**
>
> Defaulted parameters should follow all mandatory parameters.

```javascript
const greet = (greeting, name = 'Guest') => greeting + ' ' + name

console.log(greet('Hello'))     // "Hello Guest"
console.log(greet('Hi', 'Tom')) // "Hi Tom"
```