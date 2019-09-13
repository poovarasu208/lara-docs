#OWASP(*)
- [Introduction](#introduction)
- [ Key Factors Of Security](#security_factors)
- [ ZAP ](#zap)
- [ZAP Key Functions](#zap-key-functions)

<a name="introduction"></a>
## Introduction
The Open Web Application Security Project (OWASP) is a non-profit organization dedicated to providing unbiased, practical information about application security. 

<a name="security_factors"></a>
## Key Factors Of Security
Six important security concepts that should be considered during web application development phase are:

- Confidentiality: Vital data should be accessible only to authorised users

- Authentication: It helps establish the identity of the user

- Authorisation: To authorise the user, he/she need to perform an action or receive a service like OTP

- Integrity: The security measure allows the receiver to determine that the data is correct

- Availability: Communication and information should be readily available, as required

- Non-repudiation: It helps prevent later denial of an action that happened 

<a name="zap"></a>
## ZAP
[`url`](https://www.owasp.org/index.php/OWASP_Zed_Attack_Proxy_Project)

The Zed Attack Proxy (ZAP) is an open source tool maintained under Open Web Application Security Project (OWASP) that has a huge community of developers speedily offering new modules or add-ons.

Once url and browser entered, ZAP executes scanning as follows

![image](/images/owasp_scanning_image.png)

 After completing scanning for the given url it displays alerts on vulnerabilities as
 
 ![image](/images/owasp_response_image.png)
 
 <a name="zap-key-functions"></a>
 ## ZAP Key Functions
 - [Man-in-the-middle Proxy](https://github.com/zaproxy/zap-core-help/wiki/HelpStartConceptsIntercept) - It allows you to see all of the requests you make to a web app and all of the responses you receive from it. Amongst other things this allows you to see AJAX calls that may not otherwise be obvious.
 
 - [Spider](https://github.com/zaproxy/zap-core-help/wiki/HelpStartConceptsSpider) - During the processing of an URL, the Spider makes a request to fetch the resource and then parses the response, identifying hyperlinks.
 
 - [Active Scan](https://github.com/zaproxy/zap-core-help/wiki/HelpStartConceptsAscan) - Active scanning attempts to find potential vulnerabilities by using known attacks against the selected targets.
 
 - [Passive Scan](https://github.com/zaproxy/zap-core-help/wiki/HelpStartConceptsPscan) - Passive scanning does not change the requests nor the responses in any way and is therefore safe to use. Scanning is performed in a background thread to ensure that it does not slow down the exploration of an application.
 
 - [Dynamic SSL Certificates](https://github.com/zaproxy/zap-core-help/wiki/HelpUiDialogsOptionsDynsslcert) - Every data send to and received from the server is encrypted/decrypted by using the original server's certificate inside ZAP. This way, ZAP knows the plain text. To establish a SSL protected session from you (your browser), ZAP is using it's own certificate.
 
 - [WebSockets](https://github.com/zaproxy/zap-core-help/wiki/HelpAddonsWebsocketIntroduction)- ZAP is able to intercept and show WebSocket messages, set breakpoints on specific types of WebSocket messages, fuzz WebSocket messages (send lots of invalid or unexpected data to a browser or server)
 
 - [Scripts](https://github.com/zaproxy/zap-core-help/wiki/HelpAddonsScriptsScripts) - ZAP Script Add-on allows you to run scripts that can be embedded within ZAP and can access internal ZAP data structures. It supports any scripting language that supports JSR 223 
 
 - [Plug-n-Hack](https://github.com/zaproxy/zap-core-help/wiki//HelpAddonsPlugnhackPlugnhack) -  Plug-n-Hack is a proposed standard from the Mozilla security team for defining how security tools can interact with browsers in a more useful and usable way.
                  
- [API](https://github.com/zaproxy/zap-core-help/wiki/HelpStartConceptsApi) - ZAP provides an Application Programming Interface (API) which allows you to interact with ZAP programmatically.
  
 