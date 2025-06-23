> NOTE:  
> Because we haven't really learnt functions yet,
> templates have been provided so you can focus on the logic.

# Question 1

Given "isAdmin" and "isLoggedIn", complete the function to return "Access denied" if either is false.

```javascript
function checkAccess(isLoggedIn, isAdmin) {
  // Your Code Here
  return
}

console.log(checkAccess(false, false)) // "Access Denied"
console.log(checkAccess(true, false))  // "Access Denied"
console.log(checkAccess(true, true))   // "Access Granted"
```

<details>
<summary>Answer</summary>

```javascript
function checkAccess(isLoggedIn, isAdmin) {
  if (isLoggedIn === false || isAdmin === false) {
    return "Access Denied"
  }
  return "Access Granted"
}
```

</details>

# Question 2

Write a function to check the AGE of a person is under 18 or over 65 and return "Discount Applies"

```javascript
function checkDiscount(age) {
  // Your Code Here
  return
}

console.log(checkDiscount(12)) // "Discount Applies"
console.log(checkDiscount(21)) // <anything else>
console.log(checkDiscount(72)) // "Discount Applies"
```

<details>
<summary>Answer</summary>

```javascript
function checkDiscount(age) {
  return age < 18 || age > 65
    ? 'Discount Applies'
    : 'No Discount'
}
```

</details>

# Question 3

Complete the function `isEven` so that it returns `true` if a number is even, otherwise `false`.

```javascript
function isEven(input) {
  // Your code here
  return
}

console.log(isEven(1)) // false
console.log(isEven(2)) // true
console.log(isEven(3)) // false
console.log(isEven(4)) // true
```

<details>
<summary>Answers</summary>

With JavaScript, there are always many ways to skin a cat...

```javascript
return input % 2 === 0
```

```javascript
return input % 2 ? false : true
```

```javascript
return !(input % 2)
```

```javascript
return !Boolean(input % 2)
```

</details>