#kubernetes #security #authorization #authentication #gcp #k8s 

[kubernetes](/kubernetes) knows two main types of users:
- normal users
	- rely on external [identity provider](/identity%20provider)s
		- f.ex. managed by [Cloud IAM](/techstack/gcp/Cloud%20IAM.md)
- service accounts
	- managed by [kubernetes](/kubernetes)

There are two main ways to **authorize** in [GKE](/techstack/k8s/GKE.md)
- [Cloud IAM](/techstack/gcp/Cloud%20IAM.md)
	- project and [cluster](/cluster) levels
- [RBAC](/techstack/k8s/RBAC.md)
	- [cluster](/cluster) and [namespace](/namespace) levels

[API](/techstack/google/API.md) server **authenticates** in different ways
- [OpenID](/techstack/security/OpenID.md) connect tokens
	- simple identity layer on top of the [OAuth 2.0](/techstack/security/OAuth%202.0.md)
- [x509](/x509) client certificates (should be disabled)
- static passwords (should be disabled)