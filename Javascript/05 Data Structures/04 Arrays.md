# Arrays

* Arrays are ordered lists of values.
  * (They are basically objects, but the keys are indexes.)
* They are zero-based indexed (the first element is at index `0`).
* The values can be anything, even nested arrays.

## Creating Arrays

Use the square brackets `[]`.

```javascript
const numbers = [1, 2, 3, 4, 5]
const fruits = ['apple', 'banana', 'orange']
```

## `.length`

The number of elements.

```javascript
const array = ['a', 'b', 'c']
console.log(array.length) // 3
```

## Accessing Elements

```javascript
//     Index:   0    1    2
const array = ['a', 'b', 'c']
console.log(array[0]) // "a"
console.log(array[1]) // "b"
console.log(array[2]) // "c"
console.log(array[3]) // undefined (out of bounds)
```

---

## Array Manipulation

### `.push()` ⚠️

Insert at the **end** of the array. Returns the new length.

```javascript
const array = ['a', 'b', 'c']
const newLength = array.push('d')
console.log(newLength) // 4
console.log(array)     // ["a", "b", "c", "d"]
```

### `.pop()` ⚠️

Removes and returns the **last** element.

```javascript
const array = ['a', 'b', 'c']
const element = array.pop()
console.log(element) // "c"
console.log(array)   // ['a', 'b']
```

### `.shift()` ⚠️

Removes and returns the **first** element.

```javascript
const array = ['a', 'b', 'c']
const element = array.shift()
console.log(element) // "a"
console.log(array)   // ['b', 'c']
```

### `.unshift()` ⚠️

Insert at the **start** of the array. Returns the new length.

```javascript
const array = ['a', 'b', 'c']
const newLength = array.unshift('d')
console.log(newLength) // 4
console.log(array)     // ["d", "a", "b", "c"]
```

---

# Common Array Methods

## `.indexOf()`

Find the index of an element (or `-1` if not found).

```javascript
const fruits = ['apple', 'banana', 'orange']
console.log(fruits.indexOf('banana')) // 1
console.log(fruits.indexOf('pare'))   // -1
```

## `.find()`

Returns the first item that passes the predicate (true/false returning) function.

```javascript
const fruits = ['apple', 'banana', 'orange']
console.log(fruits.find(fruit => fruit.length > 5)) // "banana"
```

### `.findIndex()`

Similar to `.indexOf()`, but takes a predicate like `.find()`.

## `.forEach()`

Loops over every element of the array.

Use this instead of a `for` loop for functional programming.

```javascript
const fruits = ['apple', 'banana', 'orange']
fruits.forEach((fruit, index) => {
  console.log(index, fruit) // "0 apple", "1 banana", "2 orange"
})
```

### `.some()`

Returns `true` if at least one element passes the predicate.

```javascript
const fruits = ['apple', 'banana', 'orange']
fruits.forEach((fruit, index) => {
  console.log(fruit) // "apple", "banana"
  return fruit === 'banana'
})
```

### `.every()`

Returns `true` if every element passes the predicate.

```javascript
const fruits = ['apple', 'banana', 'orange']
fruits.forEach((fruit, index) => {
  console.log(fruit) // "apple", "banana", "orange"
  return fruit === 'banana'
})
```

## `.map()`

Loops over every element of the array, and returns a new array with the returned value.

```javascript
const fruits = ['apple', 'banana', 'orange']
const fruitLengths = fruits.map((fruit, index) => {
  return fruit.length
})
console.log(fruitLengths) // [5, 6, 6]
```

## `.reduce()`

Loops over every element of the array, returning the previously returned value to the next loop. Required an initial
value.

```javascript
const values = [1, 2, 3, 4, 5, 6]
const initialValue = 0
const sum = values.reduce((prevValue, value, index) => {
  return prevValue + value
}, initialValue)
console.log(sum) // 21
```

## `.filter()`

Loops over every element of the array, and returns a new array with elements where the predicate returned `true`.

```javascript
const fruits = ['apple', 'banana', 'orange']
const filteredFruits = fruits.filter((fruit, index) => {
  return fruit.length > 5
})
console.log(filteredFruits) // ['banana', 'orange']
```

## `.slice()`

Copies the elements from the array, and returns them.
(End value is exclusive.)

```javascript
const array = [1, 2, 3, 4, 5, 6]
const subArray = array.slice(2, 4) // (start, end)
console.log(array)                 // [1, 2, 3, 4, 5, 6] - untouched
console.log(subArray)              // [3, 4]
console.log(array.slice(0))        // [1, 2, 3, 4, 5, 6] - Copies the full array
console.log(array.slice(-2))       // [5, 6]             - Copies the last elements
```

### `.splice()` ⚠️

Remove the extracted elements from the array, and returns them.

```javascript
const array = [1, 2, 3, 4, 5, 6]
const subArray = array.splice(2, 2) // (start, quantity)
console.log(array)    // [1, 2, 5, 6] - mutated
console.log(subArray) // [3, 4]
```

## `.join()`

Joins the elements with the given separator. Returns a string.

```javascript
const fruits = ['apple', 'banana', 'orange']
const fruitString = fruits.join(';')
console.log(fruitString) // "apple;banana;orange"
```

## `.concat()`

Joins (concatenates) two arrays together.

```javascript
const a = [1, 2, 3]
const b = [4, 5, 6]
const c = a.concat(b)
console.log(a) // [1, 2, 3] - untouched
console.log(b) // [4, 5, 6] - untouched
console.log(c) // [1, 2, 3, 4, 5, 6]
```

```javascript
const a = [1, 2, 3]
const b = a.concat(4) // Works for non-arrays too.
console.log(b)        // [1, 2, 3, 4]
```

## `.reverse()` ⚠️

Reverses the array in place.

```javascript
const fruits = ['apple', 'banana', 'orange']
fruits.reverse()
console.log(fruits) // ["orange", "banana", "apple"]
```

## `.sort()` ⚠️

Sorts the array lexicographically (~alphabetically) in place, or via the given function.

```javascript
const numbers = [40, 3, 20, 5, 7]
numbers.sort()
console.log(numbers) // [20, 3, 40, 5, 7]
numbers.sort((a, b) => b - a)
console.log(numbers) // [2, 3, 5, 7, 20, 40]
```

# Method Chaining

Because many of the methods return a new array, you can call another method immediately on this new array.

```javascript
const fruits = ['apple', 'banana', 'orange']
const numbers = fruits                    // ['apple', 'banana', 'orange']
  .concat('pear')                         // ['apple', 'banana', 'orange', 'pear']
  .map(fruit => fruit.length)             // [5, 6, 6, 4]
  .filter(fruitLength => fruitLength < 6) // [5, 4]
  .sort((a, b) => b - a)                  // [4, 5]
console.log(fruits)                       // ["apple", "banana", "orange"] - untouched
console.log(numbers)                      // [4, 5]
```

---

# Best Practice

* Avoid ️⚠️ methods that **mutate** the (original) array.
    * Use `.slice()` instead of `.splice()`
    * Use `.concat()` instead of `.push()`