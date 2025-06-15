# Logging to Terminal/Console

## console.log

```javascript
console.log('Hello World!')
```

Can log expressions, which get executed before logging:

```javascript
console.log(1 + 1) // 2
```

Can log multiple items (space delimited):

```javascript
console.log('test', 1, 'is', true) // "test 1 is true"
```

## Logging levels

```javascript
// Lower-level logging (less critical)
console.trace('Trace')  // Rarely used, shows stack trace
console.debug('Debug')  // Helpful for development diagnostics
console.info('Info')    // General informational messages
console.log('Log')      // Standard logging, very common

// Higher-level logging (more critical)
console.warn('Warn')    // Indicates non-breaking issues or warnings
console.error('Error')  // Indicates serious problems or exceptions
```

## console.table

A cool extra feature!

```javascript
console.table(['wow', 'that', 'is', 'cool'])
```

Displays:

| Index | Value |
|-------|-------|
| 0     | wow   |
| 1     | that  |
| 2     | is    |
| 3     | cool  |