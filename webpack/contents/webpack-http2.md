## Prequisite
* main benefit for webpack
    * bundle -> reduce request overhead
* http2 main benefit
    * multiplexing
        * reduce request overhead

## why webpack is still needed in http2 world
* resource constrainst + dependency management
    * sever can only process limited number of requests of a time
        * server restrict the number of concurent streams
            * 100
                * browser can only make 100 concurent requests
    * js files transitive dependencies
        * need to get response to know what to request
            * need multiple round trips to get whole resources, which negate the benefit of using http2
    * code splitting

* [webpack and http2](https://stackoverflow.com/questions/37556283/what-is-the-value-of-using-webpack-with-http-2)
