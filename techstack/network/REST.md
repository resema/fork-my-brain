#protocol #http

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
- `PATCH` is used to partially update fields. It does not change any of the other values.

