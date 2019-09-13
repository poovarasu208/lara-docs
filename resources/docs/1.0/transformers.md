#Transformers
- [Introduction](#introduction)
- [Construction](#construction)
- [Parse Includes](#parse-includes)
- [Default Includes](#default-includes)
- [Parse Excludes](#parse-excludes)

<a name="transformers"></a>   
## Introduction
[`Github`](https://github.com/spatie/laravel-fractal)
         
`Transformers` give you the flexibility to create a format for JSON response that you need. By using transformers we can also do type casting, pagination results, and also nest relationships. [Fractal](https://fractal.thephpleague.com/) provides a presentation and transformation layer for complex data output.Writing a transformer is easy, here is an example of a transformer for the User model we have earlier.
 
 <a name="construction"></a>      
##Construction

Transformers can be constructed as

```php 
class UserTransformer extends TransformerAbstract
{
    public function transform(User $user)
    {
        return [
                 'id'            => (int) $user->id,
                 'name'          => (string) $user->name,
                 'email'         => (string) $user->email,
                 'address'       => (string) $user->address,
        ];
    }
}
```
 <a name="parse-includes"></a>  
##Parse Includes
Parse Includes extends the transformers that are connected via eloquent relationships. For example A User model is related with Country Model and a CountryTransformer is constructed as
```php 
class CountryTransformer extends TransformerAbstract
{
    public function transform(Country $country)
    {
        return [
            'id'            => (int) $country->id,
            'name'          => (string) $country->name,
        ];
    }
}
```        
In UserTransformer follow as

```php      
class UserTransformer extends TransformerAbstract
{
    protected $availableIncludes = ['country'];
                    
    /**
    * Response format of User model
    * @param User $user
    * @return array
    */
    public function transform(User $user)
    {
        return [
            'id'            => (int) $user->id,
            'name'          => (string) $user->name,
            'email'         => (string) $user->email,
            'address'       => (string) $user->address,
            ];
    }
                    
    /**
    * Includes country details in which the user belongs to
    * @param User $user
    * @return \League\Fractal\Resource\Item
    */
    public function includeCountry(User $user)
    {
        return $this->item($user->country, new CountryTransformer());
    }
}
```          
 And in controller call as 
 ```php        
 public function show($userId)
 {
    return \fractal()->item(User::find($userId), new UserTransformer())
                          ->parseIncludes(['roles'])
                          ->respond(SUCCESS);
 }
```
         
 to return a json response for the api.

 <a name="default-includes"></a>  
##Default Includes

Default includes loads the transformer resource of a related model once it is declared as 
```php             
protected $defaultIncludes = ['country'];
```     
 and in controller we can call as
 ```php 
 public function show($userId)
 {
 return \fractal()->item(User::find($userId), new UserTransformer())
                  ->respond(SUCCESS);
 }
  ```
 <a name="parse-excludes"></a>  
##Parse Excludes

Parse excludes is used to neglect the response of default included transformers.
For example,
Once a CountryTransformer is included in UserTransformer as default includes, it can be neglected while calling in controller as
```php 
public function show($userId)
{
       return \fractal()->item(User::find($userId), new UserTransformer())
                        ->parseExcludes(['country'])
                        ->respond(SUCCESS);
} 
```
