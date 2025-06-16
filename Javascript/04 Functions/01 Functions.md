# Functions

Javascript is a **functional** language. It encourages the use of Functions.

* Functions are **reusable** snippets of code that performs a **task**.
* Functions usually have **inputs** (parameters).
* Functions usually have an **output** (the `return` value).
* Functions can be **named** or assigned to variables.
* Functions are **called** using parentheses `()` after their name or variable.

## Standard Function

```javascript
function myFunc(input) {
  // Ooh, a code block! Local scope!
  const output = input
  return output
}
```

* Always uses a code block `{}`.
* Requires explicit `return` for output.
* Hoisted (can be used before declaration).
* Old-school. **Avoid**.

## Function Expressions

```javascript
const myFunc = function (input) {
  const output = input
  return output
}
```

* Always uses a code block `{}`.
* Requires explicit `return` for output.
* Not Hoisted (must be declared before use)
* Rarely used. If ever. **Avoid**.

## Arrow Function

```javascript
const myFunc = (input) => {
  const output = input
  return output
}
```

* Code block `{}` can be omitted if single-line.
* Parentheses `()` around parameter can be omitted if single argument.
* `return` can be omitted if single-line expression.
* Not hoisted (must be declared before use).
* Modern. **Use** often.

Example:

```javascript
const f = a => a // 😍
```

---

# Calling Functions

Call with parenthesis:

```javascript
myFunc()
```

Call with arguments:

```javascript
myFunc('hello')
```

Save the returned value:

```javascript
const result = myFunc()
```

---

# Anonymous Functions

Functions without names. Often used for single-use cases, like callbacks.

```javascript
console.log(() => {
  /* code */
})
```

We'll probably use these later on.

---

# Best Practices

* Prefer Arrow functions.
* Use clear function names.
* Keep functions to one task/responsibility.
* Avoid side-effects (Pure Functions).
* Use JS Docs to describe the function, if needed.