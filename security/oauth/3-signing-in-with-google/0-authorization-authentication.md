## Authorization
* OAuth is an authoriztion protocol
* service provider (google, github) authorize third party App through user's free will to operate based on specific scopes
* authorized the app by access token
  * access token just authorize the app to obtain or modify something about user's account. It do not show who the user is.


## Authentication
* two ways
    1. make an API endpoint whih will return user info when user reauest it with access token
    2. OpenID Connect
