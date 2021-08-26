# Overview
* authorization code is one of the [grant types](https://oauth.net/2/grant-types/)
* [flow overview](https://drive.google.com/file/d/1nBWTlk74tZHq4tnId3_jBjjAE_L_7vBU/view)

## authorization request (from user to authorize app by oauth-provider)
* create app on oauth-provider
* register redirect url


## authorization parameters
* response_type=code
* cline_id
* redirect_uri(optional)
* scope
* state
    * random string for preventing csrf
    * customized state
    * redirect parameters
* PKCE

* example
```html
https://authorization-server.com/oauth/authorize
?client_id=a17c21ed
&response_type=code
&state=5ca75bd30
&redirect_uri=https%3A%2F%2Fexample-app.com%2Fauth
&scope=photos
```


## exchnage authorization code with access token
* parameters
    * grant_type
    * code
    * redirect_uri
    * client authentication
        * client_id
        * client_secret
    * PKCE Verifier
        * code_challenge_method
        * code_challenge

## server response
* access_token
* refresh_token
* token_type
* expires

## to do
* figure out what is PKCE exactly
    * for now, I only knows that the PKCE is a way to exchange code with access token on mobile devices
