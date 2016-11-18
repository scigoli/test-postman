# Authentication
MailUp APIs use different authentication methods. Standard REST API requires OAuth 2.0 with refresh token, while transactional APIs for email and SMS use different methods. Please check out this collection of methods that you can run using Postman

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/97d88425ff91042e4fbc)


### Using OAuth 2.0 for standard REST API
Standard REST API covers all the available method except those to be used for sending one to one emails or SMS.
Authentication with OAuth requires application keys (client ID, client secret). 

```
curl -X POST -H "Content-Type: multipart/form-data; boundary=----WebKitFormBoundary7MA4YWxkTrZu0gW" 
-H "Cache-Control: no-cache" -H "Postman-Token: 6e906a80-1865-6434-1f8f-6d059802306f" 
-F "client_id=MYCLIENTID" -F "client_secret=MYCLIENTSECRET" -F "response_type=code" 
-F "redirect_uri=MYCALLBACKURL" "https://services.mailup.com/Authorization/OAuth/LogOn"
```
Watch [this video](www.mailup.it) to learn more about authentication with Standard REST API

### Custom authentication for transactional emails
First you need to create a `SMTP+ account`.

### Custom authentication for transactional SMS
First you need to create a `List secret` key.




