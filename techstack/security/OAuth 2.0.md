#authorization #authentication #security #cloud 

OAuth 2.0 is the industry-standard protocol for authorization. OAuth 2.0 focuses on client developer simplicity while providing specific authorization flows for web applications, desktop applications, mobile phones, and living room devices.

- open protocol 
- used to give someone access to an account without sharing credentials
- can be restricted to specific data and limited time
- access can be revoked
- also provides [[SSO]]

#### Roles
- client
	- application that wants to access the account data
- resource owner
	- account holder
- authorization server
	- [[authentication & authorization|authorization]] service of the account provider
- resource server
	- account provider

#### Token
- [[token]]s are random strings provided by the [[authentication & authorization|Authorization]] Server
- access token
	- has a runtime
	- can be enriched with additional information (username, roles, ...)
- refresh token
	- is issued with the access token and is used to request a new Access token from the Authorization Server if the Access Token has expired