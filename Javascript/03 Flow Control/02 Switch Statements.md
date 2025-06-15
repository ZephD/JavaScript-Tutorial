# Switch Statement

Sometimes we want to chain a lot of if-else statements.

```javascript
const item = 'test'

if (typeof item === 'string') {
  console.log('Item is a string')
} else if (typeof item === 'number') {
  console.log('Item is a number')
} else if (typeof item === 'boolean') {
  console.log('Item is a number')
} else {
  console.log('Item is something else')
}
```

But a `switch` statement can look cleaner. (Do you agree?)

```javascript
const item = 'test'

switch (typeof item) {
  case 'string':
    console.log('Item is a string')
    break
  case 'number':
    console.log('Item is a number')
    break
  case 'boolean':
    console.log('Item is a boolean')
    break
  default:
    console.log('Item is something else')
}
```

The `default` case catches all unspecified cases, similar to the `else` statement.

## Break Statement

In `switch` statements, `case` clauses will **fall through** by default:
execution continues to the next case unless a `break` is used.

The `break` will break out of the `switch` statement, continuing with any subsequent code.

This allows grouping multiple conditions:

```javascript
const item = 'test'

switch (typeof item) {
  case 'string': // Falls through
  case 'number': // Falls through
  case 'boolean':
    console.log('Item is a primitive type')
    break // Skips the rest of the switch statement.
  case 'object':
  case 'function':
    console.log('Item is a reference type')
    break // Skips the rest of the switch statement.
  default:
    console.log('Item is something else')
}

// Further code can go here
```

## Code Blocks

`case` statements can also use code blocks (to e.g. localise scope).

```javascript
const userType = 'admin'

switch (userType) {
  case 'user': {
    const role = 'basic'
    console.log('User role:', role)
    break;
  }
  case 'admin': {
    const role = 'elevated'
    console.log('Admin role:', role)
    break;
  }
}
```