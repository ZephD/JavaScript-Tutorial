# What is `package.json`?

`package.json` is a special file that lives at the root of a JavaScript project.

It **describes your project** and **manages dependencies** (the libraries your project uses).

## Why is it important?

* Lists your project’s **name**, **version**, and **description**.
* Keeps track of which **libraries** your project use.
* Defines **scripts** you can run (like `npm start` or `npm test`).
* Stores other settings like **author**, **license**, and more.

## Basic example of `package.json`

```json
{
  "name": "my-project",
  "version": "1.0.0",
  "description": "Simple example project",
  "main": "index.js",
  "scripts": {
    "start": "node index.js",
    "test": "echo \"No tests yet\""
  },
  "author": "Your Name",
  "license": "MIT",
  "dependencies": {
    "express": "^4.18.2"
  }
}
```

### JSON

Notice how this is _very_ similar to JavaScript Objects?
It's written in JavaScript Object Notation (JSON).

The key difference is that JSON needs to be able to be **written to a file** (serialised).
Therefore:
* Properties must be wrapped in quotes.
* Cannot contain functions.
* Values must be simple data types: Primitives, objects, arrays.
