#API versioning
- [Introduction](#introduction)
- [Folder Structure](#folder)
- [Why versioning API?](#why-versioning-api)
- [Routing](#routing)

<a name="introduction"></a>
## Introduction
Instead of changing the api for minor change which may affects the client interface, api versioning can be done with proper identifications.

<a name="why-versioning-api"></a>
## Why versioning API?
The key to handling changes in technology and ever arising requirements is to have versions of an API. Additions to the API as well as changes that do not break existing code using the API (which is very uncommon) can be handled within one version. If there are breaking changes, i.e. that risks breaking code that is using the API, these should be introduced in a new version of the API.


<a name="folder"></a>
## Folder Structure
 The preferred folder structure to maintain versioned api is as 
`/app/controllers/API/V1/UserController.php`.

<a name="routing"></a>
## Routing
Include in the routes as

```php
Route::group(['prefix' => 'v1'], function () {
    Route::get('user',      'API\V1\UserController@index');
    Route::get('user/{id}', 'API\V1\UserController@show');
});
    
Route::group(['prefix' => 'v2'], function () {
    Route::get('user',      'API\V2\UserController@index');
    Route::get('user/{id}', 'API\V2\UserController@show');
});
   ```