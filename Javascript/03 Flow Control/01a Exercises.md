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

# Question 4

Write a function to test if a given year is a leap year.
(Is dividable by 4, but not by 100 unless it's 400).

```javascript
function isLeapYear(year) {
  // Your code here
  return
}

console.log(isLeapYear(2020)) // true
console.log(isLeapYear(1900)) // false
console.log(isLeapYear(2000)) // true
console.log(isLeapYear(2023)) // false
```

<details>
<summary>Answer</summary>

```javascript
function isLeapYear(year) {
  if (year % 4 !== 0) return false
  if (year % 100 === 0 && year % 400 !== 0) return false
  return true
}
```

</details>

# Question 5

Write a function that takes a traffic light colour,
and returns the correct action.

```javascript
function trafficAction(colour) {
  // Your code here
  return
}

console.log(trafficAction('red'))   // "stop" 
console.log(trafficAction('amber')) // "wait"
console.log(trafficAction('green')) // "go"
```

<details>
<summary>Answer</summary>

```javascript
function trafficAction(colour) {
  if (colour === 'red') return 'stop'
  if (colour === 'amber') return 'wait'
  if (colour === 'green') return 'go'
  return 'invalid colour'
}
```

</details>

# Question 6

Write a function to check if 3 side lengths make a right angled triangle.

Hint: Use pythagoras' theorem.

```javascript
function isRightAngled(a, b, c) {
  // Your code here
  return
}

console.log(isRightAngled(3, 4, 5))   // true 
console.log(isRightAngled(5, 12, 13)) // true
console.log(isRightAngled(7, 3, 12))  // false
```

<details>
<summary>Answer</summary>

```javascript
function isRightAngled(a, b, c) {
  if (a ** 2 + b ** 2 === c ** 2) {
    return true
  }
  return false
}
```

</details>

# Question 7

Write a function to return the largest of three values.

```javascript
function maxOfThree(a, b, c) {
  // Your code here
  return
}

console.log(maxOfThree(5, 3, 1))    // 5
console.log(maxOfThree(3, 12, 10))  // 12
console.log(maxOfThree(47, 56, 98)) // 98
```

<details>
<summary>Answer</summary>

```javascript
function maxOfThree(a, b, c) {
  if (a >= b && a >= c) return a
  if (b >= a && b >= c) return b
  if (c >= a && c >= b) return c
}
```

</details>

# Question 8

Write a function to check if a value is between a min and max.

```javascript
function isBetween(value, min, max) {
  // Your code here
  return
}

console.log(isBetween(5, 3, 10))    // true
console.log(isBetween(6, 12, 14))   // false
console.log(isBetween(-5, -10, 10)) // true
```

<details>
<summary>Answer</summary>

```javascript
function isBetween(value, min, max) {
  if (min <= value && value <= max) {
    return true
  }
  return false
}
```

</details>

# Question 9

Write a function to check if a start value,
plus a number of steps of a given size,
lands on a target or not.

```javascript
function canLandOn(start, step, target) {
  // Your code here
  return
}

console.log(canLandOn(0, 2, 5))    // false - 5 isn’t reachable stepping by 2
console.log(canLandOn(10, -2, 4))  // true  - stepping backwards from 10 by -2 hits 4
console.log(canLandOn(10, -2, 3))  // false - 3 is not reachable stepping by -2
console.log(canLandOn(5, 0, 5))    // true  - no step, already at target
console.log(canLandOn(5, 0, 6))    // false - no step, but target differs
console.log(canLandOn(0, 3, 9))    // true  - 3 steps of 3 reach 9
console.log(canLandOn(0, 3, 10))   // false - 10 not multiple of 3 from 0
console.log(canLandOn(5, -1, 2))   // true  - stepping backwards 3 times
console.log(canLandOn(5, -1, 6))   // false - cannot step forwards with negative step
console.log(canLandOn(0, 5, 0))    // true  - already at target
console.log(canLandOn(0, -5, 0))   // true  - already at target with negative step
```

<details>
<summary>Answer</summary>

```javascript
function canLandOn(start, step, target) {
  // We're already on target
  if (start === target) return true
  // If no steps, must be on target
  if (step === 0) return start === target
  // if going backwards, is target not behind us?
  if (step < 0 && target > start) return false
  // Same check but for forwards
  if (step > 0 && start > target) return false
  // Check if we can reach target
  return (target - start) % step === 0
}
```

</details>

# Question 10

Try re-writing some of your functions
to have only **one return statement**,
and using the **ternary operator**.