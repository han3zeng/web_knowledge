## Overview
* express has default error handler


## scenarios
* synchronous call
    * throw error
* async
    * next(error)

* express 5.0
    * handle await error automatically

* default error handler
    * default error handler closes the connection and fails the request after you already sent the response header

* put your customized error handler at the last of the middleware function stack
