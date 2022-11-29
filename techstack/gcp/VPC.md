#google #gcp #kubernetes #k8s

VPC networks are global

### Designing principles
- when creating networks, create subnets for the regions you want to operate in
- resources across regions can reach each other without any added interconnect
- if you are a global company, choose regions around the world
- if your users are close together, choose the regin closest to them plus a backup region
- a project can have mulitple networks

Machines within the same VPC can communicate with each other through the internal [IP address](/IP%20address)

[Shared VPC](/techstack/gcp/Shared%20VPC.md) is created in one project, but can be shared and used by other projects