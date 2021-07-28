## Forward Proxy
* target user: for client/user
* request steps
    * browser -> forward proxy -> DNS -> real server
* goal:
    * keep user's ip address under anonymous

## Reverse Proxy
* request steps
    * browser -> DNS -> reverse proxy -> real server
* why use it
    1. routing
        * prerequisite
            * main website: GCP
            * blogs on wordpress
            * single domain: hanslab.com
            * use subpath to redirect request to blog (hanslab.com/blogs)
                * reverse proxy comes to be handy in this situation
    2. load balancing
    3. global server load balancing
       * usually done by service provider CDNs: cloudfare
       * choose the closet node to serve the product
    4. Enhanced Security ??
    5. cache
        * host resource in USA
        * European request, European server return cached version
    6. compressing server ???
    7. ssl server https
       * free up resource of resource server
    8. replace testing service to do A/B testing so you don't need to load heavy script in your site
        * https://www.nginx.com/blog/performing-a-b-testing-nginx-plus/
        * https://www.nginx.com/blog/performing-a-b-testing-nginx-plus/
    9. monitor and log traffic.


## Refs
* [kinsta.com](https://kinsta.com/blog/reverse-proxy/#what-is-a-reverse-proxy)
* [kinsta.com](https://kinsta.com/blog/reverse-proxy/)
