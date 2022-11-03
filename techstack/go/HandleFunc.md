#go #http #network 

```go
// HandleFunc registers the handler function for the given pattern
// in the DefaultServeMux.
// The documentation for ServeMux explains how patterns are matched.

func HandleFunc(
	pattern string, 
	handler func(ResponseWriter, *Request)) {

DefaultServeMux.HandleFunc(pattern, handler)

}
```

- the [[ResponseWriter]] value `w` is used to control the response information being written back to the client that made the [[request]], such as the [[body]] of the [[response]] or the [[status code]]
- the [[Request]] value `r` is used to get information about the request that came into the server, such as the body being sent in the case of a [[POST]] request or information about the client that made the [[request]]