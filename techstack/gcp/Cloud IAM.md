#gcp #security 

Three elements are defined in Cloud IAM access control
- Who -> identity/member
- Which -> gcp project
- What -> [role](/techstack/gcp/IAM%20role.md)s & permissions

Organised hierarchically:
- organization -> folder -> project -> resource
	- top down
		- if at organization level permissions is granted this means all projects and all those resource types