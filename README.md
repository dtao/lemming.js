Lemming.js
==========

**Lemming.js** is a library to evaluate user-input JavaScript source code in the background using a [web worker](https://developer.mozilla.org/en-US/docs/Web/Guide/Performance/Using_web_workers).

Options
-------

```javascript
// relative path to lemming.js
Lemming.options.fileName = 'lemming.js';

// how much time (in milliseconds) the lemming has to run the script
Lemming.options.timeout = 3000;

// array of external scripts (e.g., 'underscore.js') to depend on
Lemming.options.scripts = [];

// whether or not the lemming should be allowed to make AJAX requests
Lemming.options.enableXHR = false;
```

Usage
-----

```javascript
var lemming = new Lemming('source to evaluate');

lemming.onTimeout(function() {
  // if the script doesn't complete within a specified timeout
});

lemming.onResult(function(result) {
  // the result of evaluating the script, assuming it runs to completion
});

lemming.onError(function(error) {
  // the error thrown by the script, if applicable
});

lemming.onCompleted(function() {
  // a catch-all callback to run whether the script times out, throws, or finishes successfully
});

lemming.run({
  // options to override Lemming.options
});
```
