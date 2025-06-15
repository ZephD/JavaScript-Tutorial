# Class Inheritance

One class can **extend** another.

The child class inherits the parent class, but can also overwrite it's methods.

```javascript
// A generic class (parent)
class Animal {
  constructor(type) {
    this.type = type // State
  }

  // Method
  speak() {
    return '' // No sound
  }
}

// A more specific class (child)
class Pig extends Animal {
  constructor() {
    super('pig') // Pass data to the parent
  }

  // Overwrite the speak method
  speak() {
    return 'Oink!'
  }
}

const pig = new Pig()
console.log(pig.type)          // Has access to parent properties
console.log(pig.speak())       // "Oink!"
console.log(pig.super.speak()) // Can call the parent version
```