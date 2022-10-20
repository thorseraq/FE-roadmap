This repository records good articles I have read, with a few thought. Unorganized links are recorded at [Web pages I have read](./links)

- [JavaScript](#JavaScript)

- [TypeScript](#TypeScript)

- [npm](#npm)

- [pnpm](#pnpm)

- [About This page](#About-This-page)

# JavaScript
### Events in js

📫 link: [Introduction to events](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events#a_series_of_fortunate_events)

Event bubbling and capture is worth reading.

📫 link: [Event](https://developer.mozilla.org/en-US/docs/Web/API/Event) interface represents an event which takes place in the DOM. There are [a list of interfaces](https://developer.mozilla.org/en-US/docs/Web/API/Event#interfaces_based_on_event) which are based on the main Event interface. Each of those interface may support different event. Reference document to check.

### Asynchronous JavaScript

📫 link: [Asynchronous JavaScript](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous)</br>

Introduce callback, promise and async style asynchronous programming. To find out if a function is asynchronous, such as [MediaDevices.getUserMedia()](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia), check whether it returns a promise.</br>Constructor, static method of [Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) is worth reading. It explained when a promise is constructed, which part of code will be executed immediately, what state promise have, what information these states indicate and how states are transferred by calling onfulfilled function(the first parameter in function of the promise constructor) and on onRejected (the second parameter in function of the promise constructor), which impacts when Promise.prototype.then() and Promise.prototype.catch() are executed in the future.</br>[Return value](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/then#return_value) of Promise.prototype.then() is worth reading.</br>

📫 link: [Difference between Promise.any(), and Promise.race()](https://stackoverflow.com/questions/61732049/what-is-the-difference-between-promise-any-and-promise-race)

### fetch(), a more powerful api than XMLHttpRequest()

📫 link: [fetch](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Fetching_data)

Parameter of fetch can be a string or a Request object. The latter has more feature.

### Store data in client

📫 link: [Cilent-side storage](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Client-side_storage)

Web storage store key-value pairs, where key and value are both strings. Indexed DB can store structured value. SessionStorage and localStorage are worth reading.

> The first one persists data for as long as the browser is open (the data is lost when the browser is closed) and the second one persists data even after the browser is closed and then opened again.

### ES6

📫 link: [Exploring ES6](https://exploringjs.com/es6/)

# TypeScript

### Indicate a directory as a TypeScript project.
📫 link: [What is a tsconfig.json](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html)<br/>

A tsconfig.json file or xxx.json in the current directory or parent directory can be recognized by TypeScript cli - [**tsc**](https://www.typescriptlang.org/docs/handbook/2/basic-types.html#tsc-the-typescript-compiler).

### How TypeScirpt project is structured using import/export:
📫 link: [Modules](https://www.typescriptlang.org/docs/handbook/modules.html)<br/>
TypeScript implements an ECMAScript 2015(ES6) style module-loading systems, and is capable of compiling the project to various module-loading system, such as Node.js (CommonJS), require.js (AMD), UMD, SystemJS or ECMAScript 2015 native modules (ES6) . This can be configured by [module](https://www.typescriptlang.org/tsconfig#module) in the tsconfig.json file. Therefore, in TypeScript project there is no need worrying about the target platform where compiled javascript files are running, as different platforms may require different module system.

⚡ example: cnofiguring the target module-loading system
```json
{
  "compilerOptions": {
    "module": "commonjs"
  }
}
```

### How typescript module system resolves module path
📫 link: [Module Resolution](https://www.typescriptlang.org/docs/handbook/module-resolution.html)<br/>

There are two types of paths when `import {SomeClass} from "some_path_is_put_here"`: Relative path and Non-relative path. When resolving there two kinds of paths, two strategies are used, Classic(for backwards compatibility) and Node(recommended). These two are similar. Very detailed examples are showed in above article. [baseUrl](https://www.typescriptlang.org/tsconfig#baseUrl) and [paths](https://www.typescriptlang.org/tsconfig#paths) can be configured to impact non-relative path resolving. Note once path is configured to imply path mapping, non-relative resolving rule will be breaked. Examples in [Path-mapping](https://www.typescriptlang.org/docs/handbook/module-resolution.html#path-mapping) shows this.



### A test framework testing for modern web apps.
📫 link: [Playwright](https://playwright.dev/)

#### demo

📫 link: [The Example Test](https://playwright.dev/docs/next/writing-tests)

#### Run/Debug test and see reports

📫 link: [Running Tests](https://playwright.dev/docs/next/running-tests)

Run all tests, a single test file, a set files, etc. Debug and show reports.

#### config file: playwright.config.js / playwright.config.ts

📫 link: [Configuration](https://playwright.dev/docs/next/test-configuration)

#### run test with GitHub Actions

📫 link: [GitHub Actions](https://playwright.dev/docs/next/ci-intro#github-actions)

# npm

### Manage packages using npm

📫 link: [Using npm packages in your projects](https://docs.npmjs.com/using-npm-packages-in-your-projects)

install lodash locally, package.json, package-lock.json file is generated automatically. **But how is non-relative path resolved?**

Reproduce instructions:
```bash
mkdir demo && cd demo
npm install loadsh
touch hello.js
# copy the following content to hello.js
```

file `hello.js`, Can't run with `node hello.js`. Compiling hello.ts with tsc generates the same style.
```javascript
var _ = require('loadsh');

var array = [1];
var other = _.concat(array, 2, [3], [[4]]);

console.log(other);
```

file `hello.js`, run with `node hello.js` successfully
```javascript
var _ = require('./node_modules/loadsh');

var array = [1];
var other = _.concat(array, 2, [3], [[4]]);

console.log(other);
```

### install package using npm install

📫 link: [npm-install](https://docs.npmjs.com/cli/v8/commands/npm-install)

`npm install some_package` will install the package locally, by default with `latest` tag, creating a node_modules folder, a package.json file and a package-lock.json file. See [What is the role of the package-lock.json?](https://stackoverflow.com/questions/44297803/what-is-the-role-of-the-package-lock-json).</br>

`npm install` in a folder with package.json, but without package-lock.json, will install all the dependencies specified in package.json, with satisfied version. </br>

`npm install` in a folder with package.json, package-lock.json will install all the dependencies in package.json, but with version specified in package-lock.json.</br>

To install packages globally, refer to [Downloading and installing packages globally](https://docs.npmjs.com/downloading-and-installing-packages-globally)</br>

To install with specified version, tag, url, etc, refer to [npm-install](https://docs.npmjs.com/cli/v8/commands/npm-install). </br>

What is npm tag: [How to use: npm tags](https://dev.to/andywer/how-to-use-npm-tags-4lla)



### semantic version number in package.json

📫 link: [npm-install](https://docs.npmjs.com/about-semantic-versioning)

# pnpm

### Difference between pnpm and npm

📫 link: [npm-install](https://pnpm.io/motivation)

I haven't seen other difference between npm and pnpm, yet, and will take pnpm as npm by far.

# About This page

## How do I batch add "📫 link: " symbols: 

1. Search with `^\[.*\]`, to find all lines start with a [xxx].</br>
2. Select all occurrences</br>
3. Enter `Home` to move cursor to the line start.</br>
4. Paste "📫 link: ".