#gcp #cloud 

Managed instance groups create [[VM]]s based on [[instance template]]s.

- instance templates define VMs: image, machine type, etc.
- [[instance group manager]] creates the machines
- set up [[auto scaling]] to optimize cost and meeti varying user workloads
- add a [[health check]] to enable [[auto healing]]
- use [[multiple zones]] for high availability