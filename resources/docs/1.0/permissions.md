# User Permissions (Roles and Rights)

- [Introduction](#introduction)
- [Usage](#usage)
- [Packages](#package)

<a name="introduction"></a>
##Introduction
Roles represent a collection of users that are assigned permissions by an administrator to perform similar actions or functions. A user can belong to one or more roles. If a user is a member of more than one role their access permissions are merged.

<a name="usage"></a>
##Usage
  Include Roles in model to allow its usage
```php
class User extends Authenticatable
{
    use HasRoles;
    
    // ...
}
```
      
To create roles and its associated permissions follow as
 ```php
$role = Role::create(['name' => 'writer']);
$permission = Permission::create(['name' => 'edit articles']);
```           
       
A permission can be assigned to a role using 1 of these methods:
```php
 $role->givePermissionTo($permission);
 $permission->assignRole($role);
```   

Multiple permissions can be synced to a role using 1 of these methods:
```php
$role->syncPermissions($permissions);
$permission->syncRoles($roles);
```   

A permission can be removed from a role using 1 of these methods:
 ```php
$role->revokePermissionTo($permission);
$permission->removeRole($role);
```  
        
A role can be assigned to any user:
```php
$user->assignRole('writer');
``` 

A permission can be given to any user:
```php
$user->givePermissionTo('edit articles');
```
        
<a name="package"></a>
##Packages
###Spatie/laravel-permission
[`Github`](https://github.com/spatie/laravel-permission)   [`Packagist`](https://packagist.org/packages/spatie/laravel-permission) 

This package allows you to manage user permissions and roles in a database.