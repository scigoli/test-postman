# test-postman
_Press the button below to open a test suite in Postman_

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/6a93e95a9669e43b665c)

This project provides a sequence of commands to be called 

1. Login as an admin
2. Create a dish
3. Create another dish
4. Modify the first dish
5. Delete all the dishes

```
  curl --request POST \
  --url http://localhost:3000/users/register \
  --header 'content-type: application/json' \
  --data ' {"username":"usrAdmin","password":"pwdAdmin","firstname":"me","lastname":"myself" }'
```


[PHP Sample](https://gist.github.com/scigoli/ebe88538f58dc3ee00083f802fe51c6d)

The documentation is also available on [Online Postman Documenter](https://documenter.getpostman.com/collection/view/996393-72e02c9a-3331-a6a8-bda4-658519557f40).

To test the method on your account or to get more snippet you may also [Run in Postman](https://www.getpostman.com/collections/6a93e95a9669e43b665c)

New to Postman? Check out this video

[![IMAGE ALT TEXT](http://img.youtube.com/vi/JZP2ose-OBQ/0.jpg)](https://youtu.be/JZP2ose-OBQ)

[Secondary](secondary.md)

[Wiki](https://github.com/scigoli/test-postman/wiki)
