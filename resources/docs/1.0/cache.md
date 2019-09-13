# Cache

- [Introduction](#introduction)
- [Redis connection](#redis-connection)
- [Memcached connection](#memecached-connection)
- [Cache usage](#cache-usage)

<a name="introduction"></a>
## Introduction
Cache is storing something temporarily for fast retrieval later on.It stores HTTP responses temporarily for fast retrieval later on thereby reducing the number of requests made to the server. Due to which less bandwidth is consumed and web server load is reduced. It also helps users to visit a web page if web server is down.
By default, Laravel is configured to use the  file cache driver, which stores the serialized, cached objects in the filesystem. For larger applications, it is recommended that you use a more robust driver such as Memcached or Redis. Include `CACHE_DRIVER` in .env file to use the required driver.
 
<a name="redis-connection"></a>
## Redis connection
Before using Redis with Laravel, you will need to install the predis/predis package via Composer
```php 
composer require predis/predis
```
The Redis configuration for your application is located in the config/database.php configuration file. 

<a name="memecached-connection"></a>
## Memcached connection

Using the Memcached driver requires the [`Memcached PECL`](https://pecl.php.net/package/memcached) package to be installed. You may list all of your Memcached servers in the `config/cache.php` configuration file:
```php 
'memcached' => [
    [
        'host' => '127.0.0.1',
        'port' => 11211,
        'weight' => 100
    ],
],
```    
<a name="cache-usage"></a>
## Cache usage
[`Documentation`](https://laravel.com/docs/5.7/cache)

The Cache facade provides convenient and easy way of accessing cache

#### Retrieving 
The get method on the Cache facade is used to retrieve items from the cache.
```php 
Cache::get('key')
```    
 Pass a second argument to the `get` method specifying the default value to be returned if the item doesn't exist
```php  
Cache::get('key', 'default')
```
 Passing a Closure allows you to defer the retrieval of default values from a database or other external service
```php  
Cache::get('key', function () {
    return DB::table(...)->get();
});
```     
The `has` method may be used to determine if an item exists in the cache.This method will return false if the value is null or false
```php 
Cache::has('key')
```    
Retrieve all users from the cache or, if they don't exist, retrieve them from the database and add them to the cache
```php 
Cache::remember('users', $minutes, function () {
    return DB::table('users')->get();
});
```
can also use `rememberForever` method to retrieve an item from the cache or store it forever
```php 
Cache::rememberForever('users', function() {
    return DB::table('users')->get();
});
```    
#### Storing 
The put method on the Cache facade to store items in the cache. When you place an item in the cache, you need to specify the number of minutes for which the value should be cached
```php 
Cache::put('key', 'value', $minutes);
```    
The `forever` method may be used to store an item in the cache permanently. 
```php 
Cache::forever('key', 'value');
```    
The items stored with `forever` method must be removed manually using `forget` method
    
#### Removing
Remove items using
```php     
Cache::forget('key');
```
or clear entire cache using  
```php 
Cache::flush();
```
 