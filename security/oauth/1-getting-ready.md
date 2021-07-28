# Getting Ready


## Creating an Application
* creating an account on service website (FB developer)
* register your app
    * info
        * name
        * website logo
        * terms
        * etc
    * importnat info
        * one or more redirect url
            * used to redirect user after they authorize the application
* get
    * client_id, client_secret

## Redirect URLs and State
* Redirect URL
    * convey authorization code || access token
        * prevent malicious access
    * multiple URLs
        * same client_id for
            1. different services: web app, mobile app
            2. different mode: development, production
    * must be https
        * prevent the auth code from being intercepted
    * exact match
    * States
        * grant access from different paths of the app
            * home page, login page, authors page
        * state parameter used to encode application state
            * state parameter + random data
            * state parameter + PKCE
        * OAuth Service will not touch such data
        * example
            1. encode the redirect url in JWT
            2. user authorizes the app
            3. redirect user back to the app with the JWT
            4. the app parse the JTW and take user back to correct location
