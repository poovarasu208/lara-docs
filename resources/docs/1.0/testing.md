#TDD
- [Introduction](#introduction)
- [Creating Tests](#creating-tests)
- [Execution](#execution)


<a name="introduction"></a>   
## Introduction
`TDD` can be defined as a programming practice that instructs developers to write new code only if an automated test has failed. This avoids duplication of code. TDD means `Test Driven Development`. The primary goal of TDD is to make the code clearer, simple and bug-free.Laravel is built with testing in mind. In fact, support for testing with PHPUnit is included out of the box and a phpunit.xml file is already set up for your application.
    The detailed documentation for testing is described in [laravel documentation](https://laravel.com/docs/5.6/testing)
  
<a name="creating-tests"></a>   
##Creating Tests
To create a new test case, use the make:test Artisan command:

```php 
// Create a test in the Feature directory...
php artisan make:test UserTest

// Create a test in the Unit directory...
php artisan make:test UserTest --unit
```        
Once the test has been generated, you may define test methods as you normally would using PHPUnit. 
```php 
<?php
namespace Tests\Unit;
    
use Tests\TestCase;
use Illuminate\Foundation\Testing\RefreshDatabase;
class UserTest extends TestCase
{
    /**
    * A basic test example.
    *
    * @return void
    */
    public function testBasicTest()
    {
        $response = $this->json('POST', 'api/v1/user/create', ['name' => 'example', 'email' => 'example@example.com', 'password' => 'password'], ['Authorization' => 'Bearer token']);
        //If the test case fails
        $response->assertStatus(422);
        //If test case pass 
        $this->assertDatabaseHas('users',['name' => 'example', 'email' => 'example@example.com']);//to test whether data stored in database
        $response->assertStatus(200);
        //To check json response include $response->assertExactJson() by passing the expected json structure as an argument;
    }
} 
```        
<a name="execution"></a>   
## Execution 
After writing test cases one can run it in the terminal by using the command
```php         
$ vendor/bin/phpunit file path --class=testClass
example
$ vendor/bin/phpunit tests/feature/example.php
 ```       
    