#cloud #network #http 

CSP := Content Security Policy
- based on [CORS](/techstack/network/CORS.md), [HTTP](/techstack/network/HTTP.md) headers can be used to specify wether certain elements (not only scripts) are allowed to reload resources from other domains

```http
...
Content-Security-Policy: default-src 'self'; img-src *
...
```
- `default-src` 'self': in general, resources to be reloaded must originate from the original domain ('self')
- `img-src *`: images may be reloaded from any domain (`*`)