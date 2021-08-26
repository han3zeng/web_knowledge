## Overview
* self-encoded access token
    * store all rerlated info in token
    * stateless on api server
    * easy to scale up horziontally
        * since you don't have to look up info in database
* OAuth 2.0 Bearer Tokens
    * api server can change implementation without affecting client web app
* works badly with distributed system
    * invalidating token problem


## how to create it
* JSON web token format (JWT)
* jwt is a token format.
* an access token can adopt JWT format

## invalidating
* can only wait until it expires
    * typical practice
        * short-lived access tokens + long lived refresh token
* there are several ways to invalidate token
    * [source](https://stackoverflow.com/questions/21978658/invalidating-json-web-tokens)
