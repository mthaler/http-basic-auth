# http-basic-auth

The simplest form of web authentication is HTTP basic authentication. The request contains a header field in the form of Authorization: Basic <credentials> where credentials is the Base64 encoding of ID and password joined by a single colon :, e.g. `Authorisation: Basic dGVzdDpzZWNyZXQ=`

## Server
    
The server will check if the `Authorization` header field is present and if the value is a valid username / password combination.

### Examples
 

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
