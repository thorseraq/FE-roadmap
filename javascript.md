### Events in js

📫 link: [Introduction to events](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events#a_series_of_fortunate_events)

Event bubbling and capture is worth reading. 

[Event](https://developer.mozilla.org/en-US/docs/Web/API/Event) interface represents an event which takes place in the DOM. There are [a list of interfaces](https://developer.mozilla.org/en-US/docs/Web/API/Event#interfaces_based_on_event) which are based on the main Event interface. Each of those interface may support different event. To check, Reference document.

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
