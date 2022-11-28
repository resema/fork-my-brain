#protocol #http #web

REST is the abbreviation of the Representational State Transfer protocol.
It consists of the four major [[HTTP]] verbs, such as:
- `GET` is used to retrieve data
- `POST` is used to create data
	- generatores entity ID and returns it to the client
	- overwrites existing entity
- `PUT` is used to create data or alter existing data
	- Entity ID must be known
	- `PUT` should be [[idempotent]]
- `DELETE` is used to remove data

Additionally:
- `PATCH` is used to partially update fields. It does not change any of the other values
- **not** all [[HTTP Verbs|Verbs]] have to be implemented

#### Details
- [[HTTP]] as a resource-oriented architectural principle
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
- resource identification via [[URI]]
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
	- [[HMAC]] - Keyed-Hash Message Authentication Code
		- shared secret ca be determined via hash code, so e.g. client [[authentication & authorization|authentication]] is possible
	- [[OpenID]] and [[OAuth 2.0]]
		- secure authentication; rights transfer for applications
	- for XML-based messages, e.g. [[XML Encryption]]