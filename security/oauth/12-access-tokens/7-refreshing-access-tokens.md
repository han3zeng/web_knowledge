## Refreshing Access Tokens
* grant_type (required)
    * grant_type === 'refresh_token'
* refresh_token (required)
* scope (optional)
* Client Authentication (required if provided)


## verifying the fresh token grant
1. check if required parameters exist
2. check if Client Authentication are valid
3. check if refresh token is valid and has not expired
4. check if refresh token is at the right person's hand

## Issue Refresh Token
* respond
    * new valid access token
    * The server may issue a new refresh token in the response, but if the response does not include a new refresh token, the client assumes the existing refresh token will still be valid.

* example
    * check the website


## refs
* [oatuh.com](https://www.oauth.com/oauth2-servers/access-tokens/refreshing-access-tokens/)
* [example - google oauth](https://developers.google.com/identity/protocols/oauth2/web-server#offline)
