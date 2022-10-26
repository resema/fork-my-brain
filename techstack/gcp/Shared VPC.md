#gcp #cloud 

Requires an organization
- create the [[VPC]] in the host project
- shared VPC admin shares the [[VPC]] with other service projects

Allows centralized control over network configuration
- network admins configure [[subnet]]s, [[firewall rule]]s, [[route]]s 
- remove network admin rights from developers
- developers focus on machine creation and configuration in the shared network
- disable the creation of the default network using an organizational policy