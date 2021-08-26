## Successful Response

#### parameters
* access_token (required)
* token_type (required)
    * bearer
* expires_in (recommended)
* refresh_token (optional)
    * implicit grant === off
* scope (optional)

#### http headers
* Cache-Control: no-store
* Pragma: no-cache
    * no-store: don't cache
    * no-cache: do validation
        * need validator (ETag)

* example

```

HTTP/1.1 200 OK
Content-Type: application/json
Cache-Control: no-store
Pragma: no-cache

{
  "access_token":"MTQ0NjJkZmQ5OTM2NDE1ZTZjNGZmZjI3",
  "token_type":"bearer",
  "expires_in":3600,
  "refresh_token":"IwOGYzYTlmM2YxOTQ5MGE3YmNmMDFkNTVk",
  "scope":"create"
}
```

#### Access Token format
* no defined structure for [bearer token](https://datatracker.ietf.org/doc/html/rfc6750)
* valid characters: alphanumeric + following punctuation `-._~+/`

* **Typically a service will either generate random strings and store them in a database along with the associated user and scope information**

* where to store info
    * database:
        * access token
        * associated user and scope information
    * client side
        * [self encoded token](https://www.oauth.com/oauth2-servers/access-tokens/self-encoded-access-tokens/)
            * token string itself contains all the necessary info
                * **what info??**

## Unsuccessful Response
* parameters
    * error (required)
    * error_description (optional)
        * intend for application developer
    * error_uri (optional)
        * intend for application developer
        * for your api documentation

* possible values for error parameter
    * http status: 400
        * invalid_request
        * invalid_grant
            * invalid auth code or password
            * invalid redirect url
        * invalid_scope
        * unauthorized_client
            * This client is not authorized to use the requested grant type.
        * unsupported_grant_type
    * http status: 401
        * invalid_client
            * invalid client_id or client_secret

* example
```
  HTTP/1.1 400 Bad Request
  Content-Type: application/json;charset=UTF-8
  Cache-Control: no-store
  Pragma: no-cache

  {
    "error": "invalid_request",
    "error_description": "Request was missing the 'redirect_uri' parameter.",
    "error_uri": "See the full API docs at https://authorization-server.com/docs/access_token"
  }
```
