# Logical Operators

Lets say that:

```javascript
const a = true
const b = false
````

## AND: `&&`

True if **both** values are Truthy.

```javascript
console.log(a && b) // false
```

## OR: `||`

True if **either** values are Truthy.

```javascript
console.log(a || b) // true
```

## NOT: `!`

Inverts the truthiness of the variable.

```javascript
console.log(!a) // false
console.log(!b) // true
```

Inverting twice is a good way to convert truthiness to a boolean.

```javascript
console.log(!!a) // true
```

---

# Short Circuiting

These checks use **short-circuiting**.
They skip redundant subsequent checks (saving CPU resources).

```javascript
function funcTrue() {
  console.log('F1')
  return true
}

function funcFalse() {
  console.log('F2')
  return false
}

funcFalse() && funcTrue() // funcTrue is not called

funcTrue() || funcFalse() // funcFalse is not called
```
