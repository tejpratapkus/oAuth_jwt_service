>Register User

```
curl --location 'http://localhost:8080/api/auth/register' \
--header 'Content-Type: application/json' \
--data '{
    "userName": "tej",
    "password": "tej123"
}'
```

>Login User

```
curl --location 'http://localhost:8080/api/auth/login' \
--header 'Content-Type: application/json' \
--data '{
    "userName": "tej",
    "password": "tej123"
}'
```

>Get New Token

```
curl --location 'http://localhost:8080/api/auth/token' \
--header 'Content-Type: application/json' \
--data '{
    "userId": "{{userId}}",
    "accessToken": "{{accessToken}}",
    "refreshToken": "{{refreshToken}}"
}'
```

>Get User By Passing userId & Token

```
curl --location --globoff --request GET 'http://localhost:8080/api/users/{{userId}}' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {{accessToken}}' \
--data '{
    "userId": "{{userId}}",
    "accessToken": "{{accessToken}}",
    "refreshToken": "{{refreshToken}}"
}'
```

>Set Global Variable in Postman Test Section

```
pm.test("Your test name", function () {
    var jsonData = pm.response.json();
    console.log(jsonData.userId);
    pm.globals.set("userId", jsonData.userId);
    pm.globals.set("accessToken", jsonData.accessToken);
    pm.globals.set("refreshToken", jsonData.refreshToken);
});
```

![image](https://github.com/tejpratapkus/oAuth_jwt_service/assets/50861834/bde2ec02-73f6-4b36-9f98-7d2425a03b8a)



