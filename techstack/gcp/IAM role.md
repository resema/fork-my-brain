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
2. predefined [[Cloud IAM]] roles
	- provide granular acces to [[kubernetes]] resources
		- [[GKE]] Viewer
			- read-only permissions to [[cluster]] and kubernetes resources
		- [[GKE]] Developer
			- full access to kubernetes resources within clusters
		- [[GKE]] Admin
			- full access to clusters and their kubernetes resources
		- [[GKE]] Cluster Admin
			- create/delete/update/view clusters
			- **no** access to kubernetes resources
3. custom roles