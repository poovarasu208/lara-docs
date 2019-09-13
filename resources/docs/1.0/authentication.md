# Authentication
- [Introduction](#introduction)
- [JWT](#jwt)
- [Middleware Construction](#middleware)
- [Create Token](#authenticate)
- [Expire Token](#expire)

<a name="introduction"></a>
##Introduction
APIs typically use tokens to authenticate users and do not maintain session state between requests. We use JWT for Authentication

<a name="jwt"></a>
##JWT
[`Github`](https://github.com/tymondesigns/jwt-auth)   [`Documentation`](https://jwt-auth.readthedocs.io/en/develop/)  [`Packagist`](https://packagist.org/packages/tymon/jwt-auth) 

A `JSON Web Token (JWT)` is a JSON object that is defined in RFC 7519 as a safe way to represent a set of information between two parties. The token is composed of a header, a payload, and a signature.

<a name="middleware"></a>
##Middleware Construction
Construct a middleware to display the error codes for JWT token errors

```php
try {
   // Get the token from request. Throws exception if token is null
   if (!$token = $this->auth->setRequest($request)->getToken()) {
    //error code response for token not provided
   }
        
   // Get the user from the token
   if (!$user = $this->auth->authenticate($token)) {
    //user not found error response
    }
        
    $this->events->fire('tymon.jwt.valid', $user);
} catch (TokenExpiredException $exception) {
    //Token expired error
} catch (TokenInvalidException $exception) {
    //Token invalid error
} catch (JWTException $exception) {
    //Jwt exception error 
} catch (\Throwable $exception) {
//Other exceptional errors
}
```

<a name="authenticate"></a>       
##Create Token
Creating a JWT token would be to authenticate the user via their login credentials, and if successful return a token corresponding to that user using attempt() method as follows
```php 
$credentials = $request->only('email', 'password');
$token = JWTAuth::attempt($credentials)
```
  
<a name="expire"></a>      
##Expire Token
To expire a token or to logout an user you have to get the token from request headers and then invalidate it as follows

```php
$token = JWTAuth::getToken();
JWTAuth::invalidate($token);
```