# Push Notification
- [Introduction](#introduction)
- [SNS](#sns)
- [SNS Implementation](#sns-implementation)

<a name="introduction"></a>   
## Introduction
[`Notifications`](https://laravel.com/docs/5.6/notifications)

Push notification is the process of delivering information from the back end application to end user’s mobile device without any request from the end user. We can send the push notifications from Laravel application using AWS SNS service easily.

<a name="sns"></a>   
## SNS
AWS SNS (Simple Notification Service) is a flexible, fully managed push notification service provided by Amazon web services. Using this, we can send messages to individuals or large numbers of recipients. Amazon SNS makes it simple and cost effective to send push notifications to mobile device users, email recipients or even send messages to other distributed services.

FCM is a cross-platform messaging solution that allows us to send messages for both Android and Apple devices.

<a name="sns-implementation"></a>   
## SNS Implementation

- Create a project in Firebase and get the Legacy server key for Cloud messaging.

- Create an application in AWS SNS with GCM platform.It creates an ARN for your application.Then add the this ARN in your .env file

    ######example: ANDROID_APPLICATION_ARN=arn:aws:sns:us-east-1:9273842649560:app/GCM/Test-Application

- Use the following package [`aws-sdk-php-laravel`](https://github.com/aws/aws-sdk-php-laravel).This makes the developers to access Amazon Web Services in Laravel code.And Add your AWS credentials in aws.php config file.

-  we need to get the device tokens with the corresponding platform from User App to send push notifications by generating endpoint ARN using AWS ARN for the device  and store it in database

- It is more efficient to send push notifications through queues using the already generated ARN

To get a detailed knowledge on sending push notifications visit [How to Send Push notifications using Laravel and AWS SNS](http://blog.mallow-tech.com/2017/03/how-to-send-push-notifications-using-laravel-and-aws-sns/) in mallow blog
