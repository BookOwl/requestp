#requestp
requestp is a promise based wrapper around XMLHttpRequest. You still get all the power of XMLHttpRequest, but you pass the arguments as a object and use .then() instead of event handlers, which leads to cleaner code.

##Examples
Requesting a web page:
```
requestp({method: "GET", url: "http://example.org/"}).then(function(data){ console.log(data); });
```
Requesting and parsing a JSON file:
```
requestp({method: "GET", url: "http://example.org/example.json"}).then(JSON.parse).then(
  function(data) {console.log(data.key); }
);
```