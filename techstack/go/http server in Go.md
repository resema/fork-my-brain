#go #http #network 

The Go standard library provides built-in support for creating an [HTTP](/techstack/network/HTTP.md) server to serve web content or making HTTP requests to those servers.

- Listening for [request](/request)s and serving [response](/response)s
	- http.[HandleFunc](/techstack/go/HandleFunc.md) to tell the server which function to call to handle a request to the server
	- http.[ListenAndServe](/techstack/go/ListenAndServe.md) to start the server and tell it to listen for new HTTP requests and serve the using the handler functions set up
- http.[ServeMux](/ServeMux)

[a link to a good article](/https://www.digitalocean.com/community/tutorials/how-to-make-an-http-server-in-go)