# Strings

* Strings are sequences (arrays) of characters.
* Strings are immutable (cannot be changed). Methods return new strings.

## String Literals

```javascript
const myString = 'Hello world!'
```

`"` (double) or `'` (single) quotes can be used. Single is preferred.

## String Objects

```javascript
const myString = new String('Hello World!')
```

Rarely used. Useful for converting things to strings.

## String Templates

* Uses backticks `` ` ``.
* Can embed Javascript expressions using `${}`.

```javascript
const items = 6
const myString = `There ${items === 1 ? 'is' : 'are'} ${items} item${items === 1 ? '' : 's'}.`
console.log(myString) // "There are 6 items"
```

---

# String Indexing

```javascript
const myString = 'Hello World!'
console.log(myString[0]) // "H"  
console.log(myString[8]) // "r"  
```

---

# String Concatenation

```javascript
const myString = 'Hello' + ' ' + 'Tom'
console.log(myString) // "Hello Tom"
```

---

# String Escaping

```javascript
const quote = 'It\'s a Lovely day!'
```

---

# Common String Methods

## `.length`

Get the length of the string (number of characters).

```javascript
const myString = 'Hello World!'
console.log(myString.length) // 12
```

## `.toUpperCase()` / `.toLowerCase()`

Converts the text to upper or lower case.

```javascript
const greeting = 'Hello World'
console.log(greeting.toUpperCase()) // "HELLO WORLD"
console.log(greeting.toLowerCase()) // "hello world"
```

## `.trim()`

Remove whitespace from the start and end of the string.

Useful for sanitising user input.

```javascript
const messy = '  hello  '
console.log(messy.trim()) // "hello"
```

## `.includes()`

Check if the string contains a specific substring (case-sensitive). Returns `true` or `false`.

```javascript
const phrase = 'JavaScript is fun'
console.log(phrase.includes('Script')) // true
console.log(phrase.includes('script')) // false
```

## `.indexOf()`

Find the position of the first match of a substring (case-sensitive). Returns `-1` if not found.

```javascript
const phrase = 'Find the needle in the haystack'
console.log(phrase.indexOf('needle')) // 9
console.log(phrase.indexOf('cat'))    // -1
```

## `.slice()` / `.substring()`

Extracts part of a string by specifying start and end (exclusive) indexes.

```javascript
//            0123456789
const word = 'JavaScript'
console.log(word.slice(0, 4)) // "Java"
console.log(word.substring(4, 10)) // "Script"
```

## `.replace()`

```javascript
const text = 'I love cats'
console.log(text.replace('cats', 'dogs')) // "I love dogs"
```

## `.split()`

Splits a string into an array of substrings by a separator.

```javascript
const phrase = 'JavaScript is fun'
console.log(phrase.split(' ')) // ["JavaScript", "is", "fun"]
```

## `.startsWith()`

```javascript
const phrase = 'JavaScript is fun'
console.log(phrase.startsWith('Java')) // true
```