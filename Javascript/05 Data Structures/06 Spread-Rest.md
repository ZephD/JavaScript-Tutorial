# Spread (`...`)

Spread (iterates) values from an object or array.

```javascript
const baseUser = {
  role: 'user',
  active: true,
}

const tom = {
  ...baseUser,
  name: 'tom',
  age: 27,
}
console.log(tom) // { role: "user", active: true, name: "tom", age: 27 }

const adminUser = {
  role: 'admin', // is overwritten by baseUser - Oops!
  ...baseUser,
  active: false, // overrides baseUser
}
```

```javascript
const array = [1, 2, 3]
const copy = [...array]
```

```javascript
const array1 = [1, 2]
const array2 = [3, 4]
const merged = [...array1, ...array2]
console.log(merged) // [1, 2, 3, 4]
```

# Rest (`...`)

Collects the "rest" of the items.

Can be used with arrays. Groups into an array.

```javascript
const numbers = [10, 20, 30, 40]
const [first, ...rest] = numbers
console.log(first)  // 10
console.log(rest) // [20, 30, 40]
```

Can be used on objects. Groups into a new object.

```javascript
const obj = { a: 1, b: 2, c: 3 }
const { b, ...rest } = obj
console.log(b)    // 2
console.log(rest) // { a:1, c:3 }
```

Can be used on function parameters. Groups into an array.

```javascript
const sum = (...numbers) => numbers.reduce((prev, val) => prev + val, 0)
console.log(sum(1, 3, 5, 7)) // 16
```
