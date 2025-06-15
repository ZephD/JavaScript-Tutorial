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

---

# Short Circuiting

These checks use **short-circuiting**.
They skip redundant subsequent checks (saving CPU resources).

```javascript
function f1() {
  console.log('F1')
  return true
}

function f2() {
  console.log('F2')
  return false
}

f2() && f1() // f1 is not called, as f2 returned false.

f1() || f2() // f2 is not called, as f1 already returned true.
```
