#cloud #network #http #https

#### Example
`http://www.itech-progress.com:80/index.php?title=academy#web`

- [URI](/techstack/network/URI.md) = Uniform Resource Identifier
- transmitted from the [HTTP](/techstack/network/HTTP.md) client to the [HTTP](/techstack/network/HTTP.md) server
- addresses a file on the http server
- [port](/port) only required if different from standard port
	- [HTTP](/techstack/network/HTTP.md): 80, [HTTPS](/techstack/network/HTTPS.md): 443
- path and query contain information for identifying the resource
- fragment references a part within the resource
	- scheme: `http:`
	- authority: `//www.itech-progress.com:80`
	- path: `/index.php`
	- query: `?title=academy`
	- fragment: `#web`

- used by [GraphQL](/GraphQL), [gRPC](/techstack/google/gRPC.md) and others