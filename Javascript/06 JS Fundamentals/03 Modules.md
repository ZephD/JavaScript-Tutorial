# Modules

Complex code should be separated into separate files.

Like with functions, each file should have **one responsibility**.

> Note: Remember to set `{ "type": "module" }` in your `package.json`.

## Named Exports

You can `export` a variable or function from a file to share it with other files.

```javascript
// File: math.js
export const add = (a, b) => a + b
export const subtract = (a, b) => a - b
```

## Import

To import the file into your code, use the `import` statement.

Named variables use the `{}` notation.

```javascript
// File: app.js
import { add, subtract } from './math.js'

console.log(add(1, 2)) // 3
```

Note:

* `./` means same directory as current file.
* `../` means one directory up from current file.

You can also rename the named function.

```javascript
import { add as sum } from './math.js'
```

## Export Default

Often, a file only has one thing to export (e.g. a React Component).
In this case, you can export it as a default.

Files can only have **one** default export.

```javascript
// File: greet.js
const greet = name => `Hello ${name}!`

export default greet
```

```javascript
// File: app.js
import greet from './greet.js'

console.log(greet('Tom')) // "Hello Tom!"
```

You can name the default import whatever you like.

```javascript
import hello from './greet.js'
```

## Mixing Exports

It's totally valid to use both named exports and a default export.

```javascript
// File: useColour.js
export const RED = 'red'
export const GREEN = 'green'
export const BLUE = 'blue'

const useColour = colour => colour.toLowerCase()

export default useColour
```

```javascript
// File: app.js
import useColour, { RED } from './useColour.js'

const style = {
  backgroundColor: useColour(RED),
}
```