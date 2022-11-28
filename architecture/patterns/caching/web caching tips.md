#architecture #pattern #web #cache

- consistent use of [[URL]]s
	- a document should always have the same [[URL]] (even on different pages)
- let caches store constant images and pages
- specify appropriate max-age or expiry time
- do not unnecessarily change files
- reduce the usage of [[Cookies]]
- reduce [[encryption]]
	- encrypted pages are not stared by shared caches
- [[POST]] only if necessary
	- also [[PUT]] and [[DELETE]] not cacheable
- avoid user-specific information in the [[URL]]
- set field "content-length" in the [[HTTP]] response headers
	- if the length is unknown, the server closes the connection after transmission