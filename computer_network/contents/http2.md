## HTTP2 impact

* Multiplexing
    * overview
        * http1
            * request 1 -> response 1 -> request 2 -> response 2....
            * each request may create new connection
        * http2 (multiplexing)
            * request (1,2,3,4....n) -> one response
                * the response has all requested data
            * multiple parallel request in single connection
    * detail
        * http1
            * each request: request -> establish connection -> response
            * one after another. If one block, others can not be loaded
        * http2
            * multiple requests have single connection
            * multiple requests have single response
                * each requested data has special number to identify them, so requester can assemble data and at its end and render it separately

* Sever push
* Header Compression
    * more advanced


## To Read
* [Developer Google](https://developers.google.com/web/fundamentals/performance/http2)

## refs
* [http2 - cloudflare](https://www.cloudflare.com/learning/performance/http2-vs-http1.1/)
