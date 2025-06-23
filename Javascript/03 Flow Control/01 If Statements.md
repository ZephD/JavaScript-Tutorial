# Conditional Scoping

Sometimes we want to run a block of code, only if a particular condition is met.

## If Statement

"If (condition is true) then { run this code }".

```javascript
const value = 7

if (value === 7) {
  // Ooh, a code block! Local scope!
  console.log('The value is seven!') // Prints
}
```

## Else Statement

"... else { run this code }"

```javascript
if (value === 7) {
  console.log('The value is seven!')     // Prints
} else {
  console.log('The value is NOT seven!') // Does not print
}
```

Only **one** of the code blocks get executed.

## Else-If Statements

```javascript
if (value === 0) {
  console.log('The value is zero')
} else if (value > 0) {
  console.log('The value is positive')
} else if (value < 0) {
  console.log('The value is negative')
}
```

## Single-Line If

```javascript
if (value === 7) console.log('Hi there!')
```

No need for code block if one-line.

## Ternary Operator

* condition
* `?` then
* `:` else

```javascript
let result // Yucky undefined let
if (value === 0) {
  result = 'The value is zero'
} else {
  result = 'The value is not zero'
}
console.log(result)
```

Can be written:

```javascript
const result = value === 0
  ? 'The value is zero'
  : 'The value is not zero'
console.log(result)
```

Can be nested:

```javascript
const result = value === 0
  ? 'The value is zero'
  : value < 0
    ? 'The value is negative'
    : 'The value is positive'
console.log(result)
```

Use whichever gives the best clarity or convenience.

<details>
test
</details>