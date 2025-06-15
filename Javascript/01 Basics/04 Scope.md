# Scoping

## Blocks

Blocks are defined by curly braces `{}`.

Code inside blocks is typically indented for readability.

```javascript
{
  // A code block!
}
```

(Top-level anonymous blocks like this are rare in JavaScript.)

## Variable Scoping

Variables have scope, determining where they are accessible.

* Variables declared at the top level are **globally scoped** (accessible inside nested blocks).
* `const` and `let` are **block scoped** — limited to the block they are declared in.
* `var` is **function scoped**, not block scoped — it ignores block boundaries.
  * This often leads to unanticipated errors, hence why we normally avoid using `var`.
* Local variables override outer variables **only within their block**.


```javascript
const a = 'global'
const b = 'global'

{
  console.log(a) // "global"

  // Creating a local 'b' variable
  const b = 'local'
  console.log(b) // "local"

  // Creating a 'var' variable
  var c = 'global'
}

console.log(b) // "global"
console.log(c) // "global" - Not block scoped!
```
