# Front End Checklist
   - [Blade Templates](#blade-templates)
   - [Assets](#assets)
   - [Bootstrap](#bootstrap)
   - [X-CSRF-TOKEN](#X-CSRF-TOKEN)
   - [Script](#script)
   - [Packages](#packages)
   - [Themes](#themes)


<a name="blade-template"></a>
## Blade Template

[Blade](https://laravel.com/docs/blade) is the simple, yet powerful templating engine provided with Laravel.

Blade view files use the  `.blade.php` file extension and are typically stored in the `resources/views` directory.


<a name="assets"></a>
## Assets

All Your JavaScript, CSS, and images should be in `public/assets` folder.

>{success}  [Learn more about Assets in Laracast]( https://laracasts.com/series/laravel-5-fundamentals/episodes/19) .
 
<a name="bootstrap"></a>
## CSS
### Bootstrap

[Bootstrap](https://getbootstrap.com/) is an open source toolkit for developing with HTML, CSS, and JS
 
 
<a name="script"></a>
## Script
### jQuery Plugin

[jQuery](https://jquery.com/) is a fast, small, and feature-rich JavaScript library.
    
  
<a name="X-CSRF-TOKEN"></a>
## X-CSRF-TOKEN   
```php 
<meta name="csrf-token" content="{{ csrf_token() }}"> 
```

include this meta tag in root view file `app.blade.php` in the `views/layouts` directory 
  
  
<a name="packages"></a>
## Packages   
#### Laravel Debugbar 

[Laravel Debugbar](https://github.com/barryvdh/laravel-debugbar) debug the app using it. 

> {success}  [Learn more about Debugging in Laracast](https://laracasts.com/series/lets-build-a-forum-with-laravel/episodes/20) .
   
   

<a name="theme"></a>
##Themes

####[Voyager](https://laravelvoyager.com/) 

Voyager is a Laravel Admin Package that includes BREAD(CRUD) operations, a media manager, menu builder, and much more.
 
[View on Github](https://github.com/the-control-group/voyager)

####[LaraAdmin ](http://laraadmin.com/) 

A Simple and Fast way to built Admin Panel in Laravel as well as a CRM

[View on Github](https://github.com/dwijitsolutions/laraadmin)

####[QuickAdmin](https://github.com/LaravelDaily/quickadmin)  

No packages required. No syntax to learn. Just generate and download clean Laravel code

[View on Github](https://github.com/LaravelDaily/quickadmin)

