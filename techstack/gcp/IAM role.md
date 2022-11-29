#gcp #security #cloud #authorization #authentication 

Three different types of IAM roles
1.  basic roles 
	- grant global, project-level access
		- Vierwer role
			- Read-only permissions
		- Editor role
			- write permissions
			- all permissions of a viewer role
		- Owner role
			- manage roles and permissions
			- setup project billing
			- all permissions of an editor role
2. predefined [Cloud IAM](/techstack/gcp/Cloud%20IAM.md) roles
	- provide granular acces to [kubernetes](/kubernetes) resources
		- [GKE](/techstack/k8s/GKE.md) Viewer
			- read-only permissions to [cluster](/cluster) and kubernetes resources
		- [GKE](/techstack/k8s/GKE.md) Developer
			- full access to kubernetes resources within clusters
		- [GKE](/techstack/k8s/GKE.md) Admin
			- full access to clusters and their kubernetes resources
		- [GKE](/techstack/k8s/GKE.md) Cluster Admin
			- create/delete/update/view clusters
			- **no** access to kubernetes resources
3. custom roles