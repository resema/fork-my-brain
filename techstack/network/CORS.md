#cloud #network #http 

CORS := Cross-Origin Resource Sharing
- for security reasons, script by default only reload resources that are hosted by the same domain os the original website [[request]]
- additional [[HTTP]] headers can be used to reload resources from certain other domains
```http
HTTP/1.1 200 OK
...
Access-Control-Allow-Origin: https://other-1.com
...
```
origin Server: https://origin.com
- allowed: other server 1 https://other-1.com
- **not** allowed: other server 2 https://other-2.com