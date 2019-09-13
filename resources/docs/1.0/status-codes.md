# Status Codes

- [Introduction](#introduction)
- [Commonly used codes](#status-codes)

<a name="introduction"></a>   
## Introduction
Status codes are issued by a server in response to a client's request made to the server. It includes codes from IETF Request for Comments (RFCs), other specifications, and some additional codes used in some common applications of the Hypertext Transfer Protocol (HTTP).        

<a name="status-codes"></a> 
##Commonly used codes
The commonly used status codes are as follows

| Code | Definition | Description|
| --- | --- | --- |
| 200 | Success | The request was successful |
| 201 | Created | The request was successful and a resource was created |
| 204 | No Content | The request was successful but there is no representation to return (that is, the response is empty) | 
| 400 | Bad Request | The request could not be understood or was missing required parameters | 
| 401 | Unauthorized | Authentication failed or user does not have permissions for the requested operation | 
| 403 | Forbidden | Access denied | 
| 404 | Not Found | Resource was not found | 
| 405 | Method Not Allowed | Requested method is not supported for the specified resource | 
| 409 | Conflict | Requested method is Conflict with other method. Ex: Data delete operation not done, because child row available | 
| 422 | Validation Error | Requested input is not satisfied | 
| 5xx | Server Side Error | Server side Error Occur | 