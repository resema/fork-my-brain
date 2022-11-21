#cloud #network #http #https

#### Example
`http://www.itech-progress.com:80/index.php?title=academy#web`

- [[URI]] = Uniform Resource Identifier
- transmitted from the [[HTTP]] client to the [[HTTP]] server
- addresses a file on the http server
- [[port]] only required if different from standard port
	- [[HTTP]]: 80, [[HTTPS]]: 443
- path and query contain information for identifying the resource
- fragment references a part within the resource
	- scheme: `http:`
	- authority: `//www.itech-progress.com:80`
	- path: `/index.php`
	- query: `?title=academy`
	- fragment: `#web`

- used by [[GraphQL]], [[gRPC]] and others