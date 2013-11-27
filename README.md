Lemming.js
==========

**Lemming.js** is a library to evaluate user-input JavaScript source code in the background using a [web worker](https://developer.mozilla.org/en-US/docs/Web/Guide/Performance/Using_web_workers).

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
    fileName: 'relative path to lemming.js (defaults to just "lemming.js")',
    timeout: 'how much time (in milliseconds) the lemming has to run the script (defaults to 3000)'
});
```
