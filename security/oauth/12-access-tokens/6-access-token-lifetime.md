## short lived access token + long-lived access token
* features
    * work with self-encoded token
    * access token
        * last seceral hours to couple weeks
        * short-lived so the provider can haver chance to revoke access
    * refresh token
        * never expires
        * get new access token by refresh token
        * use it behind the scene without user's involvement
    * as oatuh provider, you have to offer easy refreh token mechanism for thrid-party developer

* when to use it
    * implement self-encoded token
    * you want to limit the risk of leaked access tokens
    * you will be providing SDKs that can handle the refresh logic transparently to developers

* note
    * why refresh token can limnit the risk of leadked access tokens
        * Because the access token is short-lived and the refresh token has never been exposed to user (browser). The system will store refresh token in api server or database. Only when the access token expire then the system fetch the refresh token and use it to obtain latest valid access token

## Shortl-lived access tokens without refresh token
* features
* when to use it
    * you want to the most protection against the risk of leaked access tokens
    * you want to force users to be aware of third-party access they are granting
    * you don’t want third-party apps to have offline access to users’ data
        * example: the web app can't continually sync data

## Non-expiring access tokens
* features
    * easy to develope
    * don't use it with sefl-encoded token if you want to revoke them arbitarily
    * need to store the token in in database
        * you can delete, invalidate them

* when to use it
    * you have a mechanism to revoke access tokens arbitrarily
    * you don’t have a huge risk if tokens are leaked
    * you want to provide an easy authentication mechanism to your developers
    * you want third-party applications to have offline access to users’ data

## Terms
* offline access token
    * your app obtain refresh token
    * you app can obtain valid access token by refresh token
    * your app can access to user data without user's consent

## refs
* [oauth.com](https://www.oauth.com/oauth2-servers/access-tokens/access-token-lifetime/)
* [off-line access](https://stackoverflow.com/questions/30637984/what-does-offline-access-in-oauth-mean)
