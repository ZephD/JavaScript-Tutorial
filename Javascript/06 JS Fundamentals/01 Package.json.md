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
  "type": "module",
  "main": "index.js",
  "scripts": {
    "start": "node index.js",
    "test": "echo \"No tests yet\""
  },
  "author": "Your Name",
  "license": "MIT",
  "dependencies": {
    "react": "^19.1.0",
    "react-dom": "^19.1.0"
  },
  "devDependencies": {
    "eslint": "^9.25.0"
  }
}
```

Properties of note:

* `name` the name of your app.
* `type: module` lets us use the modern module syntax.
* `main` the entry-point of your app.
* `scripts` useful scripts like running, building or testing your app.
* `dependencies` contains libraries used by the app during run-time.
* `devDependencies` contains libraries used during development only.

### JSON

Notice how this is _very_ similar to JavaScript Objects?
It's written in **J**ava**S**cript **O**bject **N**otation (JSON).

The key difference is that JSON needs to be able to be **written to a file** (serialised).
Therefore:

* Its properties must be strings (using double quotes).
* It cannot contain functions.
* Its values must be simple data types: Primitives, objects, arrays.
