#architecture #pattern #web #cache

- consistent use of [URL](/techstack/network/URL.md)s
	- a document should always have the same [URL](/techstack/network/URL.md) (even on different pages)
- let caches store constant images and pages
- specify appropriate max-age or expiry time
- do not unnecessarily change files
- reduce the usage of [Cookies](/techstack/network/Cookies.md)
- reduce [encryption](/techstack/security/encryption.md)
	- encrypted pages are not stared by shared caches
- [POST](/POST) only if necessary
	- also [PUT](/PUT) and [DELETE](/DELETE) not cacheable
- avoid user-specific information in the [URL](/techstack/network/URL.md)
- set field "content-length" in the [HTTP](/techstack/network/HTTP.md) response headers
	- if the length is unknown, the server closes the connection after transmission