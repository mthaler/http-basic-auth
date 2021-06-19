# http-basic-auth

Example code showing how to implement HTTP basic auth in Go

##

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
