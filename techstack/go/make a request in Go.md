#go #network #http 

In contrast to `http.Get` , the `http.Request` function provides you with greater control over the [[request]], other than just the [[HTTP]] method and the [[URL]] being requested

```go
http.Get

http.Request
```

#### Example GET Request
```go
// create a GET request
req, err := http.NewRequest(http.MethodGet, requestURL, nil)

// send the GET request and receive a response
res, err := http.DefaultClient.Do(req)
```

