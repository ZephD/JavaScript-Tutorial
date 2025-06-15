# Variables

You "assign" data to a named variable, so you can reference that variable later on and use it

(e.g. logging the content of the variable to the terminal)

## var

```javascript
var myVar = 'toast'
console.log(myVar) // "toast"
```

`var` is old school - do not use

## let

A variable that can be reassigned

```javascript
let myLet = 'cake'
console.log(myLet) // "cake"
myLet = 'biscuit'  // Reassigned
console.log(myLet) // "biscuit"
```

## const

A variable that **cannot** be reassigned

```javascript
const myConst = 'doughnut'
myConst = 'something else' // ERROR

const myCopy = myConst + 'jam'
console.log(myCopy)  // "doughnutjam"
console.log(myConst) // "doughnut" - unchanged

```

## Dynamically Typed

JavaScript is **dynamically typed**, meaning variables are **not bound to a specific type**.

```javascript
let myString = 'test'
console.log(myString) // "test"

myString = 123;       // Changed from String to Number
console.log(myString) // 123
```

## Naming Variables

#### Required (Syntax Rules)
- Cannot be a reserved keyword (e.g. `let`, `class`, `const`)
- Cannot start with a number (e.g. `1var`)
- Are case-sensitive (e.g. `userName` ≠ `UserName`)
- Can include letters, digits, `$`, and `_` (e.g. `user_1`, `$temp`)
- Cannot contain spaces or special characters (e.g. `user name`, `@var`)

#### Recommended (Best Practices for Clarity)
- Use `camelCase` for variables and functions (e.g. `userEmail`)
- Use **meaningful, descriptive names** (e.g. `totalPrice`, not `a` or `data`)
- Prefix booleans with `is`, `has`, or `can` (e.g. `isAdmin`, `hasAccess`)
- Use short names where well known (e.g. `i` in loops)

| Case Style               | Example   | Common Use                                  |
|--------------------------|-----------|----------------------------------------------|
| **camelCase**            | `maxRam`  | JavaScript variables, functions, filenames   |
| **PascalCase**           | `MaxRam`  | JavaScript classes, React components         |
| **SCREAMING_SNAKE_CASE** | `MAX_RAM` | Constants (JS, Python, C)                    |
| **snake_case**           | `max_ram` | Python variables, file names                 |
| **kebab-case**           | `max-ram` | URLs, CSS class names, file names (web)      |
