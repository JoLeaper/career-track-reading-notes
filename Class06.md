# Class 06 Reading

## HTTP
- HTTP: Hyper Text Transfer Protocol
- Applications built using HTTP are users of the client-server copmuting model.
- Client-Server Model: Servers are hosts designed to provide services, Clients are hosts that make requests to those services. 
- HTTP serves .html files, but also does images, videos, .json, .xml, binary executables, and more.

## HTTP Requests
- HTTP requsts are formatted in text and formatted using TCP (trasnport-layer protocol). The first line contains the method, url, and the HTTP version. The subsequent lines are the header (A header is like a key:value pair. if there is more than one value in the header, it's separated using a semi-colon). Terminated with empty line, optional body follows.
- Example: 
```html
REQUEST EXAMPLE:

POST /api/note HTTP/1.1
Host: api.example.com
Origin: www.example.com
Authorization: Bearer bHVsIHRoaXMgaXMgYSBmYWtlIHNlY3JldCB0b2tlbg==
Accept: application/json
Content-Type: application/json; charset=UTF-8
Content-Length: 58

{"title":"kata","content":"get 100 points on hacker rank"}
```

```html
HTTP/1.1 200 OK
Date: Tue, 22 Aug 2017 06:34:16 GMT
Content-Type: application/json; charset=UTF-8
Content-Encoding: UTF-8
Content-Length: 82
Last-Modified: Mon, 21 Aug 2017 12:10:38 GMT
Server: Apache/1.3.3.7 (Unix) (Red-Hat/Linux)
ETag: "3f80f-1b6-3e1cb03b"
Connection: close

{"id":"1234123412341324","title":"kata","content":"get 100 points on hacker rank"}
```
| HTTP Method  |  Request Has Body | Response Has Body  | Safe  |  Idempotent | Cacheable | Function 
|---|---|---|---|---|---|---|
|  GET |  NO |  YES | YES  | YES  |  YES |  Retrieve a resource  |
|  HEAD |  NO |  NO | YES  |  YES | YES  |  Like GET but headers only  |
|  POST |  YES | YES  | NO  | NO  | YES  |  Create a resource  |
|  PUT  |  YES | YES  |  NO | YES  | NO  | 	Update a resource   |
|  DELETE |  NO | YES  | NO  | YES  | NO  |  Delete a resource  |
|  CONNECT  | YES | YES  |  NO | NO  | NO  |  Create TCP/IP tunnel  |
| OPTIONS  |  OPTIONAL | YES  | YES  | YES  | NO  | 	Returns supported methods for a URL   |
|  TRACE | NO  | YES  |  YES | YES  | NO  | 	Echos retrieved request   |
| PATCH  | YES  | YES |  NO | NO  | NO  |  	Partial modification of resource  |

- SAFE: Should only be used for informational retrieval, not used for changing server state.
- IDEMPOTENT: If two identical requests are made, they should get an identical response.
- CACHEABLE: Client caches the response.


## REST

- Representational State Transfer. 
- A means which we can reference, manipulate, and transfer state.
- RESTFUL Endpoint: Performing CRUD (create, read, update, delete) operations over HTTP.
- EXAMPLE: http://api.server.com/api/v1/people

| REST Method | Crud Operation | Function
|---|---|---|
| GET | READ | Retrieve 1 or More Records |
| POST | CREATE | Create a new record |
| PUT | UPDATE | Update a record through replacement |
| PATCH | UPDATE | Update a specific part of a record |
| DESTROY | DELETE | Remove a record |