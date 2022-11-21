#kubernetes #security #authorization #authentication #gcp #k8s 

[[kubernetes]] knows two main types of users:
- normal users
	- rely on external [[identity provider]]s
		- f.ex. managed by [[Cloud IAM]]
- service accounts
	- managed by [[kubernetes]]

There are two main ways to **authorize** in [[GKE]]
- [[Cloud IAM]]
	- project and [[cluster]] levels
- [[RBAC]]
	- [[cluster]] and [[namespace]] levels

[[API]] server **authenticates** in different ways
- [[OpenID]] connect tokens
	- simple identity layer on top of the [[OAuth 2.0]]
- [[x509]] client certificates (should be disabled)
- static passwords (should be disabled)