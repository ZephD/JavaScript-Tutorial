# Libraries

Libraries are external snippets of code that your code can use to save time and add features.

JavaScript has a _massive_ collection of libraries (over 3.1 million) built by the community.

## NPM - Node Package Manager

`npm` is the **default package manager** for Node.js.
It helps you:

* **Find and install** libraries (called *packages*) from the huge npm registry.
* Manage your project's **dependencies** in `package.json`.
* Run useful **scripts**, like testing or building.
* Share your own packages with others.

**Basic commands:**

* `npm init` - provides a wizard to help create `package.json`.
* `npm install <package>` - add a package to your project.
* `npm uninstall <package>` - remove a package.
* `npm update` - update all packages.
* `npm run <script>` - run a script defined in `package.json`.

## Yarn

[Yarn](https://yarnpkg.com/) is a popular alternative to npm with a focus on speed and reliability.

* Installs packages faster by caching files.
* Uses a lockfile (`yarn.lock`) to ensure consistent installs.
* Has similar commands: `yarn add`, `yarn remove`, `yarn run`.

## Useful Libraries

* `lodash` - Collection of powerful functions.
* `moment` - Functions to handle dates and times.
* `react` - Application building toolset using `.jsx`.
* `axios` - Promise-based HTTP client for making API requests.
* `express` - For building HTTP web servers.
* `jest` - A testing framework.