#gcp #cloud 

Requires an organization
- create the [VPC](/techstack/gcp/VPC.md) in the host project
- shared VPC admin shares the [VPC](/techstack/gcp/VPC.md) with other service projects

Allows centralized control over network configuration
- network admins configure [subnet](/subnet)s, [firewall rule](/firewall%20rule)s, [route](/route)s 
- remove network admin rights from developers
- developers focus on machine creation and configuration in the shared network
- disable the creation of the default network using an organizational policy