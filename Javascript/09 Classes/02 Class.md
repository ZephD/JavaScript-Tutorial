# Classes

Javascript supports both **functional** and **object-oriented** styles.

JavaScript added object-orientated-like syntax to appeal to object-oriented developers.

```javascript
class Counter {
  constructor() {
    this.count = 0
  }

  increment() {
    this.count++
    return this.count
  }
}

const couter = new Counter() // An instance of Counter
console.log(couter.increment()) // 1
console.log(couter.increment()) // 2
```

* The `constructor()` runs when you call `new Counter()`.
* `this` refers to instance of the object being created.
* Methods can be created in the class.

## Constructor Arguments

You can pass argument into the constructor to initialise state.

```javascript
class Circle {
  constructor(x, y, radius = 1) {
    this.position = { x, y }
    this.radius = radius
  }
}

const circle = new Circle(0, 0)
console.log(circle.position.x) // 0
console.log(circle.position.y) // 0
console.log(circle.radius)     // 1
```

## Private State

Fields marked with `#` are private - they cannot be accessed outside of the class.

```javascript
class Counter {
  #count // Declare field

  constructor() {
    this.#count = 0
  }

  increment() {
    // Can be used within the class
    this.#count++
    return this.#count
  }
}

const counter = new Counter()
console.log(counter.increment()) // 1
console.log(counter.count)       // undefined

// Cannot be used outside the class
console.log(counter.#count)      // Syntax Error 
```

## Static Methods

Classes can have `static` methods, which are used from the Class, not the instance of the class.

```javascript
class MathTools {
  static square(n) {
    return n * n
  }
}

console.log(MathTools.square(2)) // 4
```