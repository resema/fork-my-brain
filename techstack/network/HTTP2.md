#cloud #network #http/2 #protocol 

- [[TCP]]-based network protocol
	- [[HTTP]] is **not**
- is implemented in all modern browsers today
- goal is to reduce the response time between browser and server to realize a real interaction
	- handshaking in [[HTTP]] in the beginning costed too much time
	- handshaking in HTTP/2 is encoded in binary
		- called [[multiplex]]ing (see also [[server multiplexer|Golang's multiplexer]])
		- multiple documents can be sent, f.ex. `styles.css` and `scripts.js` at the same time

[live demo](http://www.http2demo.io/)
