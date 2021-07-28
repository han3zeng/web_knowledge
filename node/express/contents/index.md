## Express
* routing + middleware  functions
    * routing: route method + route path
* series of middleware calls

* dissect structure
    *
    ```js
      app.get('/user', function (req, res, next) {
        ...
      })
      // a. app.get: route method
      // b. '/user': route path
      // c. (req, res, next) => {}: middleware
      // a + b + c: route handler

      app.get('/user', function(req, res, next){})
      app.get('/admin', function(req, res, next){})
      // the two middlewwares are in same stack

      app.get('/user',function (req, res, next) {}, function (req, res, next) {})
      // multiple middleware in singe route handler: middleware sub-stack
    ```


## [middleware function](http://expressjs.com/en/guide/using-middleware.html)
* what is it
    * is function that has access to the request / response object and next middleware
* what does it do
    * execute code
    * modify req, res object
    * invoke next turn the process to next handler
    * end the request-response cycle


## Endpoint
* what is endpoint
    * route method + route path


## next middleware function
* if you pass anything other than the string 'route' or 'router', the express will trigger error handling function
  * [refs](http://expressjs.com/en/guide/writing-middleware.html)
* [next('route')](http://expressjs.com/en/guide/using-middleware.html#middleware.router)
    * skip the rest of the middleware functions from router-middleware-stack === middleware sub-stack
    * work only in middleware functions that were loaded by using the app.METHOD() or router.METHOD() functions.
    * app - level
* To skip the rest of the router’s middleware functions, call next('router') to pass control back out of the router instance.
    * router - level


## Note
* To pass some result from current middleware function to next middleware function, just create a new property of req object and set the value.
* mount path === route path
* So when you add a custom error handler, you must delegate to the default Express error handler, when the headers have already been sent to the client:
    * http://expressjs.com/en/guide/error-handling.html


## ToRead
* [using middleware](https://expressjs.com/en/guide/using-middleware.html)
    * Router-level middleware
    * Error-handling middleware
