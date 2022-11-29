#go #http #network 

HandleFunc registers the [Handler](/Handler) function for the given pattern in the DefaultServeMux. The documentation for [ServeMux](/ServeMux) explains how patterns are matched.

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

- the [ResponseWriter](/techstack/go/ResponseWriter.md) value `w` is used to control the response information being written back to the client that made the [request](/request), such as the [body](/body) of the [response](/response) or the [status code](/techstack/network/status%20code.md)
- the [Request](/Request) value `r` is used to get information about the request that came into the server, such as the body being sent in the case of a [POST](/POST) request or information about the client that made the [request](/request)

#### Example
```go
package main

import (
	"io"
	"log"
	"net/http"
)

func main() {
	h1 := func(w http.ResponseWriter, _ *http.Request) {
		io.WriteString(w, "Hello from a HandleFunc #1!\n")
	}
	h2 := func(w http.ResponseWriter, _ *http.Request) {
		io.WriteString(w, "Hello from a HandleFunc #2!\n")
	}

	http.HandleFunc("/", h1)
	http.HandleFunc("/endpoint", h2)

	log.Fatal(http.ListenAndServe(":8080", nil))
}
```