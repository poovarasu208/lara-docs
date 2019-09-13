# Error Codes
- [Introduction](#introduction)
- [Error code format](#error-code-format)
- [Error code generation](#error-codes)

<a name="introduction"></a>   
## Introduction
Error codes in the response stage of an API is the fundamental way in which a developer can communicate failure to a user. This stage, sitting after the initial request stage, is a direct communication between client and API.Error codes have an implied value in the way that they both clarify the situation, and communicate the intended functionality.

<a name="error-code-format"></a>  
## Error code format
*Error codes should be short and easy to understand* .
The common_error response will be,

```php 
{
    "status": "Action status",
    "error":[
        {
        "message": "You are not authorized to access this detail."
        "code": "error code",
        }
    ]
}  
 ``` 
 
<a name="error-codes"></a>  
## Error code generation  
To generate a error code with this format,we have to create a codes file in config folder with a name of error_codes.php 
  
For example
  
In error_codes.php in config returns as
```php 
return[
    'register' => [
        'email' => [
            'required' => [
                'message' => 'Email required',
                'code' => 'RV1001'
            ],
        ]
    ]
];
```
        
  Here `'register'` is the route name , `'email'` is the validation key  and `'required'` is the validation rule
 The UserRequest class extends a CustomRequest class in order to overwrite failedValidation() method to generate custom error codes as
 
 ```php 
class UserRequest extends CustomRequest
{
    /**
     * Determine if the user is authorized to make this request.
     *
     * @return bool
     */
    public function authorize()
    {
        return true;
    }

    /**
     * Get the validation rules that apply to the request.
     *
     * @return array
     */
    public function rules()
    {
        return [
          'email' => 'required'
        ];
    }
}
 ```
 And overwritten logic for failedValidation() in CustomRequest class is as
 
 ```php 
class CustomRequest extends FormRequest
{
    /**
     * Determine if the user is authorized to make this request.
     *
     * @return bool
     */
    public function authorize()
    {
        return true;
            
    /**
     * Get the validation rules that apply to the request.
     *
     * @return array
     */
    public function rules()
    {
        return [
    }                          
    /**
    * Overwriting error code generation
    * @param Validator $validator
    */
    protected function failedValidation(Validator $validator)
    {
        $response = array();
        $response['status'] = 'error';
        $attribute = $validator->failed();
        foreach ($attribute as $key => $value) {
            if (preg_match('/.[0-9]/', $key)) {
                $key = preg_replace('/.[0-9]/', '.*', $key);
            }
            foreach ($value as $rule => $item) {
                $response['error'][] = config('codes.' . Request::route()->getName() . '.' . $key . '.' . strtolower($rule));
            }
        }
        throw new HttpResponseException(response()->json($response, 422));
    }
}
 ```