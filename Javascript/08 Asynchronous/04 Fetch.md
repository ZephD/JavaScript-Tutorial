# Fetch

`fetch()` is a built-in JavaScript function to get data from a URL, like calling and API.

It returns a **promise**, so you can use `.then()` or `await`.

```javascript
fetch('https://pokeapi.co/api/v2/pokemon/1')
  .then(response => response.json()) // convert response to JSON
  .then(data => {
    console.log(data.name) // "bulbasaur"
  })
  .catch(error => {
    console.error('Fetch error:', error)
  })
```

Or use `async`/`await`:

```javascript
const response = await fetch('https://pokeapi.co/api/v2/pokemon/1')
if (!response.ok) {
  throw new Error('Fetch failed')
}
const data = await response.json()
console.log(data.name) // "bulbasaur"
```

# Axios

A popular library for making requests (like `fetch()`).

* It automatically parses the JSON
* It throws HTTP errors

First install with `npm install axios`

```javascript
import axios from 'axios' // Import it to your script

try {
  const response = await axios({
    baseURL: 'https://pokeapi.co/api/v2',
    url: 'pokemon/1',
    method: 'GET',
  })
  console.log(response.data)
} catch (error) {
  console.log('Axios error', error)
}
```
