#cloud #http #network 

| method  | secure | idempotent | identifialbe resource | cacheable | visible semantics |
| ------- | ------ | ---------- | --------------------- | --------- | ----------------- |
| GET     | X      | X          | X                     | X         | X                 |
| HEAD    | X      | X          | X                     | X         | X                 |
| PUT     |        | X          | X                     |           | X                 |
| POST    |        |            |                       |           |                   |
| OPTIONS |        | X          |                       | O         |                   |
| Delete  |        | (X)        | X                     |           | X                  |

```http
GET /wiki/Special:Search?search=cats&go=articles HTTP/1.1
Host: en.wikipedia.org
```
```http
HTTP/1.0 200 OK
Date: ...
Last-Modified: ...
Content-Language: en
Content-Type: text/html; charset=utf-8

The cats are a family...
```

- `POST` is used to create new resources in [[REST]]
```http
POST /send.php HTTP/1.1
Host: www.itech-progress.com
User-Agent: Mozilla/4.0
Accept: image/gif, image/jpeg, */*
Content-type: application/x-www-form-urlencoded
Content-length: 51
Connection: close

firstname=Max&name=Mustermann (or as JSON)
```

- `PUT` is used to manipulate/update existing resources in [[REST]]
```http
PUT /new.html HTTP/1.1
Host: www.itech-progress.com
Content-type: text/html
Content-length: 16

<p>New File</p>
```
```http
DELETE /file.html HTTP/1.1
```
