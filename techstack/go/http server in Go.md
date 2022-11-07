#go #http #network 

The Go standard library provides built-in support for creating an [[HTTP]] server to serve web content or making HTTP requests to those servers.

- Listening for [[request]]s and serving [[response]]s
	- http.[[HandleFunc]] to tell the server which function to call to handle a request to the server
	- http.[[ListenAndServe]] to start the server and tell it to listen for new HTTP requests and serve the using the handler functions set up
- http.[[ServeMux]]

[a link to a good article](https://www.digitalocean.com/community/tutorials/how-to-make-an-http-server-in-go)