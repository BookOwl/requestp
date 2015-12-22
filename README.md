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

##Reference
You pass arguments to the requestp function through a object with the following attributes:

`method`: Required. The HTTP method.

`url`: Required. The url you are requesting.

`headers`: Optional. An array of header objects that are used to override the headers of the request. Each header object takes the form 
```
{
  header: "The header to override",
  value:  "The new value for the header"
}
```
`mimetype`: Optional. Used to override the mime type of the request.

`user` and `password`: Optional. Used to authenticate the request.

`body`: Optional. The body of a POST request.
