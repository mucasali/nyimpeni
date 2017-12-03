# nyimpeni API
nyimpeni is file manager on private server

Nyimpeni API is a RESTful Web Service served as a communication bridge between server and client.

### HTTPS Request
Nyimpeni API can be requested through HTTP(S) Request to Nyimpeni Base URL endpoint. The HTTP(S) Header has to be used to allow proper authentication.

#### **base url**
> https://bok.cybermantra.net/api

## **1. Auth**
 this API for authenticating ( Login n Register)
 
#### **HTTPS Header**
| Header | Value | Definition |
| --- | --- | ---|
| Content-type | application/json | The Content-Type field indicates that JSON type is acceptable to send to the recipient |
| Accept | application/json | The Accept field is used to specify that JSON type is acceptable for the response |
| --- | --- | --- |

#### **API Methods**
| Endpoint | HTTP Method | Definition |
| --- | --- | --- |
| /register | POST | Endpoint for register to nyimpeni |
| /login | POST | Endpoint for login to have token |
| --- | --- | --- |

#### **API JSON Body**

----------
 **Register** 
| JSON Attribute | Type | Required | Description |
| --- | --- | :---: | --- |
| Username | String | Yes| Username of user |
| Password | String | Yes | password of user |
| ConfirmPassword | String | Yes | Confirmation password user |
| mode | String | No | for create bucket/folder on server or no. Use parameter "no_nyimpeni" for register user without create bucket/folder.  
| --- | --- | --- | --- |

*example :*

- register user with create bucket / folder
```
{
	"username" : "example",
	"password" : "exam_password",
	"confirmPassword" : "exam_password"
}
```
- register user without create bucket / folder
```
{
	"username" : "example",
	"password" : "exam_password",
	"confirmPassword" : "exam_password",
	"mode" : "no_nyimpeni"
}
```
----------


**Login**
| JSON Attribute | Type | Required | Description |
| --- | --- | --- | --- |
| Username | String | Yes| Username of user |
| Password | String | Yes | password of user |
| --- | --- | --- | --- |
*example :*
```
{
	"username" : "example",
	"password" : "exam_password"
}
```

----------

## 2. User

* Register
> this endpoint for register new member

 endpont
 ```
POST {base_url}/api/register
```
 header
 ```
 "Content-Type" : "application/json"
 ```
 body
 ```
 {
		"username": "example",
		"password": "password"
 }
  ```
 response
 ```
 {
	 "success" :  true,
	 "message" :  "create user success",
	 "data" : {
			"username":"example",
			"password":"password",
			"_id":"2342342gs6342",
			"updateAt": "2017-11-17T18:40:33.260Z",
		    "createdAt": "2017-11-17T18:40:33.260Z"
	  }
 }
 ```
