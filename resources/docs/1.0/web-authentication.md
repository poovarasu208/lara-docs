# Web Authentication

   - [Authentication using Artisan ](#authentication-quickstart)
   - [CSRF Protection](#CSRF-protection)
   - [X-CSRF-TOKEN](#X-CSRF-TOKEN)
   - [Auth Middleware](#middleware)
   - [Auth Helper](#helper)
   - [Packages](#packages)

<a name="authentication-quickstart"></a>
## Authentication using Artisan

The quick way to scaffold all of the routes and views you need for authentication using one simple command.
```php
php artisan make:auth
```    
    
>{primary}This command should be used on fresh applications and will install a layout view, 
 registration and login views, as well as routes for all authentication end-points. 
 A HomeController will also be generated to handle post-login requests to your application's dashboard.
 
 
<a name="CSRF-protection"></a>
## [CSRF Protection](https://laravel.com/docs/csrf)
 
Anytime you define a HTML form in your application, you should include a hidden [CSRF](https://laravel.com/docs/csrf) token field in the form so that the CSRF protection middleware can validate the request. You may use the `@csrf` Blade directive to generate the token field:
 
```php
<form method="POST" action="/profile">
    @csrf
    ...
</form>
```

<a name="X-CSRF-TOKEN"></a>
## X-CSRF-TOKEN
```php 
<meta name="csrf-token" content="{{ csrf_token() }}">
```    
 
 Then, once you have created the meta tag, you can instruct a library like jQuery to automatically add the token to all request headers. This provides simple, convenient CSRF protection for your AJAX based applications.
 
 ```php  
$.ajaxSetup({
    headers: {
        'X-CSRF-TOKEN': $('meta[name="csrf-token"]').attr('content')
    }
});
 ```
 
 
>{success} [`Learn more about CSRF in Laracast`](https://laracasts.com/series/how-do-i/episodes/6) .
     
 <a name="middleware"></a>
 ## Auth Middleware
     
 Attach `auth middleware` to the route definition it can be used to only allow authenticated users to access a given route. 

```php 
Route::get('profile', function () {
// Only authenticated users may enter...
})->middleware('auth');
```       
     
 <a name="helper"></a> 
 ## Auth Helper

 The `auth()` function returns an authenticator instance. You may use it instead of the Auth facade for convenience.
```php  
$user = auth()->user();
```
       
 <a name="packages"></a>
 ## Packages
   
 ### Spatie/laravel-permission
 [Spatie](https://github.com/spatie/laravel-permission) package allows you to manage user permissions and roles in a database