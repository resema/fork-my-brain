#go #http #network 

```go
// ListenAndServe listens on the TCP network address addr and then calls
// Serve with handler to handle requests on incoming connections.
// Accepted connections are configured to enable TCP keep-alives.

//
// The handler is typically nil, in which case the DefaultServeMux is used.

//
// ListenAndServe always returns a non-nil error.

func ListenAndServe(addr string, handler Handler) error {
	server := &Server{Addr: addr, Handler: handler}
	return server.ListenAndServe()
}
```

- The `http.ListenAndServe` function, which tells the global [[HTTP]] server to listen for incoming requests on a specific port with an optional `http.Handler`. In your program, you tell the [[server]] to listen on `":3333"`. By not specifying an [[IP address]] before the colon, the server will listen on every IP address associated with your computer, and it will listen on [[port]] `3333`.
- `handler Handler` passes a [[server multiplexer]] or `nil` to use the default server multiplexer.
- this is a blocking call, won't finish running until program finishes or the [[http]] server is told to shut down.