#App Versioning

- [Introduction](#introduction)
- [Importance of App versioning](#app-versioning)

<a name="introduction"></a>
##Introduction
`Versioning` is the management of changes to documents, computer programs, large web sites, and other collections of information. An api hit is done from any of the platforms with required details and checks for the message to display. This api uses a method called `version_compare()` to determine the comparision between version strings.

<a name="app-versioning"></a>
## Importance of App versioning
 App versioning is used to maintain the mobile Application version updates. This is used to force or warn the users about that next version is available in store. Also it is useful when we have any major update / bug fix in the new version of the app then we want the users who are using the older version to update the app to latest version

*Set update versions required in environment file and call as follows*

```php
public function AppVersionStatus(Request $request)
{
    $input = $request->only('app_version', 'os_version or android_version', 'device_model', 'platform');
    if (isset($input['app_version']) && isset($input['platform'])) {
        // android or ios user's to compare is set as environment variables
            if ((version_compare($input['app_version'], env(android or ios user's force update version)) == -1)) {
               // version status response for force update
            } elseif ((version_compare($input['app_version'], env(android or ios user's update version)) == -1)) {
                   // version status response for recommend update
            }
    }
    //return response with status code;
}
```
When the app starts, app versioning api is called to check the response for 
    
- If response is true for force update, then a popup dialog with options to either let user quit the app or force update it immediately is shown
    
- Else if response is true for recommend update,then a pop-up dialog with options to update or to continue using the app is shown.
    