# Getting Started

## Vite

Vite is the modern way to get started with a new react app.
(Previously was `create-react-app`).

We're going to keep it _super_ simple and use the **vanilla** template.

## Installing

Run this command in the terminal.

`npm create vite@latest --template vanilla`

This will give you some prompts:

* Select the `React` framework.
* Select the `JavaScript` variant.

Now run `npm install` to install all the libraries the app needs.

## Project Overview

A bunch of folders and files just got created.
Here are some important ones:

### node_modules

This contains your libraries.
Best not to look in here... It's big, and deep.

### src

This folder contains all your **source** code.

### public

This folder contains all **static** files that get hosted as-is.

Used for fonts, favicons, images.

### package.json

T

### index.html

```html
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8"/>
    <link rel="icon" type="image/svg+xml" href="/vite.svg"/>
    <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
    <title>Vite + React</title>
</head>
<body>
<div id="root"></div>
<script type="module" src="/src/main.jsx"></script>
</body>
</html>
```

Most of this is very standard html setup.
However, note the two lines within the `<body>` tag:

* `<div id="root"></div>`
    * This is the container for your React app.
* `<script type="module" src="/src/main.jsx"></script>`
    * This is the entry-point for your code.

### src/main.jsx

This is the entry-point script. This is where React _starts_.

```javascript
import { StrictMode } from 'react'
import { createRoot } from 'react-dom/client'
import './index.css'
import App from './App.jsx'

createRoot(document.getElementById('root')).render(
  <StrictMode>
    <App/>
  </StrictMode>,
)
```

This gets the `<div>` container called `root` in your `index.html` file,
and renders the top level `<App>` component.

### src/App.jsx

This is where your journey begins.

`App.jsx` is, by convention, your first React Component.

Your whole React app nests from here.

## Running

To run the app, type into the terminal:

`npm run dev`

(This runs the script `dev` in the `package.json` file.)

This starts the `vite` server, which hosts your App.

Click the link!