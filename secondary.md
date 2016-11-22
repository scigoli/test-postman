# Authentication
MailUp APIs use different authentication methods and you may need to use more than one when developing your application. 
Basically, transactional APIs for email and SMS use their own methods, while the other API methods require OAuth 2.0. Please check out this collection of methods that you can run using Postman

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/97d88425ff91042e4fbc)


### Using OAuth 2.0 for standard REST API
Standard REST API covers all the available method except for those to be used for sending transactional (i.e. one to one, not bulk) emails or SMS. Authentication with OAuth requires application keys (client ID, client secret). You need a developer account to get these keys but you can use these keys with any MailUp account.


### Custom authentication for transactional emails
First you need to create a `SMTP+ account`. Then you simply have to use the returned credentials when invoking the "send" method of transactional email API. No login method is required.

```
curl -X POST -H "Content-Type: application/json" 
-d '{  
      "User":{"Username":"SMTPPLUS_USERNAME","Secret":"SMTPPLUS_PASSWORD"}
       // other parameters...
       // check out http://help.mailup.com/display/mailupapi/Transactional+Emails+using+APIs for moe details
    }
' "https://send.mailup.com/API/v2.0/messages/sendmessage"
```
Any SMTP+ account is specific for the MailUp list it belongs to and its password does not expire.

### Custom authentication for transactional SMS
First you need to create a `List secret` key. Then you simply have to use List secret value when invoking the "send" method of transactional SMS. You can create, read and delete the "List secret" values by invoking GET, POST or DELETE methods on ```https://sendsms.mailup.com/api/v2.0/lists/MYLISTID/listsecret``` These methods require Basic Authentication by means of your MailUp account credentials. Once you have the List secret you can invoke the "send" method as much as you want without any further authentication.

```
curl -X POST -H "Content-Type: application/json;odata=verbose;charset=utf-8"  
-d '{
"Content":"Hi [Name], welcome to [City]",
"ListGuid":"MYLISTGUID",
"ListSecret":"MYLISTSECRET",
"Recipient":"RECIPIENTSNUMBER",
"CampaignCode":"Welcome messages",
"DynamicFields":[{"N":"Name","V":"John"},{"N":"City","V":"London"}],
"isUnicode":0
}
' "https://sendsms.mailup.com/api/v2.0/sms/MYACCOUNTID/MYLISTID"
```




