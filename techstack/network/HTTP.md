#protocol #cloud #network

possible response code: 3-digit HTTP status code:
- 200 codes for success
- 400 codes for client errors
	- f.ex. invalid data
- 500 codes for server errors
	- 503, f.ex. not available in case of overload

Reponse body contains resource representation.

All services need [URI](/techstack/network/URI.md) (Uniform Resource Identifiers). Is based on [TCP](/TCP).

#### Properties
- text-based stateless request-reponse application protocol
	- [HTTP2](/techstack/network/HTTP2.md) is binary
	- is [TCP](/TCP) based
		- [HTTP3](/techstack/network/HTTP3.md) is currently (Nov '22) [UDP](/UDP) based
- generic protocol for accessing resources
- [HTTP](/techstack/network/HTTP.md) verbs specify the type of access
- different representations of the same resource via [media type](/media%20type)s
- explicitly provides for intermediate processing
- provides solutions for some non-technical requirements, f.ex. scaling
- server responsed with [status code](/techstack/network/status%20code.md)s