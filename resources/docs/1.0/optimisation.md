# Memory Profile
- [Common Steps](#common-steps)
    - [Composer Autoload](#composer-autoload)
    - [Optimize with Artisan](#artisan-optimize)
    - [Config Cache](#config-cache)
    - [Route Cache](#route-cache)
    - [View Cache](#view-cache)
- [Performant Laravel](#laravel-perf)

<a name="common-steps"></a>
## Common Steps

<a name="composer-autoload"></a>
### Composer Autoload
On optimizing Composer's class autoloader map - Composer can quickly find the proper file to load for a given class.
#### To optimize
```php
composer dump-autoload -o
```
#### To reload without optimization
```php
composer dump-autoload
```
<a name="artisan-optimize"></a>
### Optimize with Artisan
#### To optimize
```php
php artisan optimize --force
```
#### To clear
```php   
 php artisan clear-compiled
```
<a name="config-cache"></a>
### Config cache
#### To cache
 ```php 
 php artisan config:cache  
 ```
#### To clear
```php
php artisan config:clear
```
This command will combine all of Laravel's configuration files into a single, cached file, which greatly reduces the number of trips the framework must make to the filesystem when loading your configuration values.
    
> {primary} If you execute the config:cache command during your deployment process, you should be sure that you are only calling the env function from within your configuration files. Once the configuration has been cached, the .env file will not be loaded and all calls to the env function will return null.

<a name="route-cache"></a> 
### Route cache
#### To cache
```php
php artisan route:cache
```

#### To clear
```php
php artisan route:clear
```
This command reduces all of your route registrations into a single method call within a cached file, improving the performance of route registration when registering hundreds of routes.

> {primary} Since this feature uses PHP serialization, you may only cache the routes for applications that exclusively use controller based routes. PHP is not able to serialize Closures.

<a name="view-cache"></a>   
### View cache
#### To cache
View will automatically get cached. 
#### To clear
If you wanna clear that cache then use the following command.
```php
php artisan view:clear
```
<a name="laravel-perf"></a>
## Performant Laravel
Performant Laravel is a new free video course created by Chris Fidao that covers quick performance wins you can implement right now into your Laravel apps.

The course includes 12 videos that range from three minutes up to twenty minutes, which makes them the perfect size for binge watching during your breaks and here is a list of all the videos included:

| Title | Description|
| --- | --- |
| The Optimize Command | Learn how the optimize command speeds up Laravel. |
| The Route Cache | Use the route cache to skip route compilation on each request. |
| The Config Cache | Use the config cache to reduce configuration parsing & see its caveats. |
| Eager Loading | Use eager loading and avoid the dreaded n+1 query problem. |
| Database Chunking | Reduce memory usage on queries returning lots of data. |
| MySQL Indexing I | Cover a sample application and the queries it makes. |
| MySQL Indexing II | Learn what a database index is & how to create a basic index. |
| MySQL Indexing III | Learn how to improve the app’s slow queries with indexes. |
| Object Caching I | Discuss and configure object caching. |
| Object Caching II | Add a naive implementation of caching. |
| Object Caching III | Use the Decorator pattern to add caching to our app. |
| Object Caching IV | Discuss ways to reduce memory usage in Redis. |

> {success} [`This course is free, but it does require a signup`](https://serversforhackers.com/laravel-perf).

