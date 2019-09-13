# Query Detection

- [N+1 query](#query)
- [Laravel Query Detector](#laravel-query-detector)
- [Laravel DB Profiler](#laravel-db-profiler)
- [Laravel Debugbar](#laravel-debugbar)

<a name="query"></a>
## N+1 query
Lets take two tables as `users` and `posts`
Construct a relation among them and if we use as follows 
```php
//Getting all user
$users = User::get();
```
Suppose if users has 100 records then to call posts we use  as

```php
//To call post of a single user we use as
foreach($users as $user){
    $posts = Post::where('user_id',$user->id);
}
```
    
It generates sql query as

```php
SELECT * FROM users;
//Calling user's post
select * from posts where user_id = 1;
select * from posts where user_id = 2;
select * from posts where user_id = 3;
and so on
```
    
This makes 1 query to select all users, then N queries to select posts for each users. So, the code produces 1+N queries.This in turn called as N+1 query which is also known as lazy loading.
    
    
<a name="laravel-query-detector"></a>
## Laravel Query Detector
[`GitHub`](https://github.com/beyondcode/laravel-query-detector) [`Packagist`](https://packagist.org/packages/beyondcode/laravel-query-detector) [`Author`](https://www.patreon.com/illuminated)

The Laravel N+1 query detector helps you to increase your application's performance by reducing the number of queries it executes. This package monitors your queries in real-time, while you develop your application and notify you when you should add eager loading (N+1 queries).

![image](/images/laravel_query_detector.png)

<a name="laravel-debugbar"></a>
## Laravel Debugbar
[`GitHub`](https://github.com/barryvdh/laravel-debugbar) [`Packagist`](https://packagist.org/packages/barryvdh/laravel-debugbar) [`website`](http://phpdebugbar.com/docs)

Have options for `QueryCollector`, `RouteCollector`, `ViewCollector`, `EventsCollector`, `LaravelCollector`, `SymfonyRequestCollector`, `LogsCollector`, `FilesCollector`, `ConfigCollector`, `CacheCollector`,

![image](/images/laravel_debugbar.png)

> {primary} You can enable/disable the collector options in `config/debugbar.php`. And this config file is available on publishing the package config files after installation.

####
> {warning}When experiencing slowness with `laravel debubgar`, try disabling some of the collectors.

### Credit Hint
> {primary} Use these query detector packages only in development. 
It can slow down the application because it has to gather data for mining the queries. 