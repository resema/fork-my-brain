#protocol #cloud #network

possible response code: 3-digit HTTP status code:
- 200 codes for success
- 400 codes for client errors
	- f.ex. invalid data
- 500 codes for server errors
	- 503, f.ex. not available in case of overload

Reponse body contains resource representation.

All services need [[URI]] (Uniform Resource Identifiers). Is based on [[TCP]].

#### Properties
- text-based stateless request-reponse application protocol
	- [[HTTP2]] is binary
	- is [[TCP]] based
		- [[HTTP3]] is currently (Nov '22) [[UDP]] based
- generic protocol for accessing resources
- [[HTTP]] verbs specify the type of access
- different representations of the same resource via [[media type]]s
- explicitly provides for intermediate processing
- provides solutions for some non-technical requirements, f.ex. scaling
- server responsed with [[status code]]s