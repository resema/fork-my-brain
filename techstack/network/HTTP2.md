#cloud #network #http/2 #protocol 

- [TCP](/TCP)-based network protocol
	- [HTTP](/techstack/network/HTTP.md) is **not**
- is implemented in all modern browsers today
- goal is to reduce the response time between browser and server to realize a real interaction
	- handshaking in [HTTP](/techstack/network/HTTP.md) in the beginning costed too much time
	- handshaking in HTTP/2 is encoded in binary
		- called [multiplex](/multiplex)ing (see also [Golang's multiplexer](/server%20multiplexer))
		- multiple documents can be sent, f.ex. `styles.css` and `scripts.js` at the same time

[live demo](/http://www.http2demo.io/)
