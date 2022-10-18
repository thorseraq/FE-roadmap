This repository records good articles I have read, with a few thought.

- [JavaScript articles](## JavaScript)

- [TypeScript articles](## TypeScript)

## JavaScript
### Events in js

📫 link: [Introduction to events](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events#a_series_of_fortunate_events)

Event bubbling and capture is worth reading.

[Event](https://developer.mozilla.org/en-US/docs/Web/API/Event) interface represents an event which takes place in the DOM. There are [a list of interfaces](https://developer.mozilla.org/en-US/docs/Web/API/Event#interfaces_based_on_event) which are based on the main Event interface. Each of those interface may support different event. Reference document to check.

### Asynchronous JavaScript

📫 link: [Asynchronous JavaScript](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous)</br>

Introduce callback, promise and async style asynchronous programming. To find out if a function is asynchronous, such as [MediaDevices.getUserMedia()](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia), check whether it returns a promise.</br>Constructor, static method of [Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) is worth reading. It explained when a promise is constructed, which part of code will be executed immediately, what state promise have, what information these states indicate and how states are transferred by calling onfulfilled function(the first parameter in function of the promise constructor) and on onRejected (the second parameter in function of the promise constructor), which impacts when Promise.prototype.then() and Promise.prototype.catch() are executed in the future.</br>[Return value](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/then#return_value) of Promise.prototype.then() is worth reading.</br>

[Difference between Promise.any(), and Promise.race()](https://stackoverflow.com/questions/61732049/what-is-the-difference-between-promise-any-and-promise-race)

### fetch(), a more powerful api than XMLHttpRequest()

📫 link: [fetch](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Fetching_data)

Parameter of fetch can be a string or a Request object. The latter has more feature.

### Store data in client

📫 link: [Cilent-side storage](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Client-side_storage)

Web storage store key-value pairs, where key and value are both strings. Indexed DB can store structured value. SessionStorage and localStorage are worth reading.

> The first one persists data for as long as the browser is open (the data is lost when the browser is closed) and the second one persists data even after the browser is closed and then opened again.

### ES6

📫 link: [Exploring ES6](https://exploringjs.com/es6/)

## TypeScript

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
