#protocol #http #web

REST is the abbreviation of the Representational State Transfer protocol.
It consists of the four major [HTTP](/techstack/network/HTTP.md) verbs, such as:
- `GET` is used to retrieve data
- `POST` is used to create data
	- generatores entity ID and returns it to the client
	- overwrites existing entity
- `PUT` is used to create data or alter existing data
	- Entity ID must be known
	- `PUT` should be [idempotent](/Glossary/idempotent.md)
- `DELETE` is used to remove data

Additionally:
- `PATCH` is used to partially update fields. It does not change any of the other values
- **not** all [Verbs](/techstack/network/HTTP%20Verbs.md) have to be implemented

#### Details
- [HTTP](/techstack/network/HTTP.md) as a resource-oriented architectural principle
	- communication protocol
	- application log
- typical REST message formats: JSON, XML
- often in industry DBs are mapped to REST endpoints
- **uniform interface**

#### Principle: Clearly Identifiable Resources
- information is described in REST as uniquely identifiable resources
- resource represents a real or virtual entity
- resource types
	- content type header
	- MIME types such as documents, images, music, videos, etc.
- resource identification via [URI](/techstack/network/URI.md)
	- ex. http://bsp.com/personenliste/4711/adresse

#### Examples
```restAPI
/users
/users/{userID}/articles
/users/{userID}/comments

/articles
/categories
/images
/comments
```

##### Bending the REST rules
```restAPI
/users/12/action/login
/users/12/action/logout
```

#### Advanced REST: Security
- for advanced security requirements, more advanced mechanisms can be used
	- [HMAC](/HMAC) - Keyed-Hash Message Authentication Code
		- shared secret ca be determined via hash code, so e.g. client [authentication](/techstack/security/authentication%20&%20authorization.md) is possible
	- [OpenID](/techstack/security/OpenID.md) and [OAuth 2.0](/techstack/security/OAuth%202.0.md)
		- secure authentication; rights transfer for applications
	- for XML-based messages, e.g. [XML Encryption](/XML%20Encryption)