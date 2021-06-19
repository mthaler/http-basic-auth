# http-basic-auth

The simplest form of web authentication is HTTP basic authentication. The request contains a header field in the form of Authorization: Basic <credentials> where credentials is the Base64 encoding of ID and password joined by a single colon :, e.g. `Authorisation: Basic dGVzdDpzZWNyZXQ=`

## Server
    
The server will check if the `Authorization` header field is present and if the value is a valid username / password combination.

### Examples
 
The [httpie](https://httpie.io/) is a user-friendly HTTP client that can be used to test the API:

#### Missing `Authorization` header

```bash
$ http http://localhost:8080
HTTP/1.1 401 Unauthorized
Content-Length: 36
Content-Type: application/json
Date: Sat, 19 Jun 2021 13:16:34 GMT
Www-Authenticate: Basic realm="Give username and password"

{
    "message": "No basic auth present"
}

```

#### Valid `Authorization` header
       
```bash
$ http http://localhost:8080 "Authorization:Basic dGVzdDpzZWNyZXQ="
HTTP/1.1 200 OK
Content-Length: 39
Content-Type: application/json
Date: Sat, 19 Jun 2021 13:38:01 GMT

{
    "message": "welcome to golang world!"
}

```
    
`dGVzdDpzZWNyZXQ=` is the Base64 encoded `test:secret` string.
    
## Client
  
The client demonstrates how to set the `Authorization` header required for HTTP basic authentication.
    
## Credits
    
The code is from [How to Implement HTTP Basic Auth in Go](https://blog.umesh.wtf/how-to-implement-http-basic-auth-in-gogolang)
