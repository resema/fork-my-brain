#gcp #k8s #kubernetes #google 

A Pod is a group of [container](/techstack/gcp/container.md)s with shared storage and networking.

Pod-to-Pod communication on the same [Node](/techstack/gcp/Node.md).
Because each node maintains a sepearate [IP address](/IP%20address) space for its [pod](/techstack/gcp/pod.md)s, the [Node](/techstack/gcp/Node.md)s don't need to perform Network Address Translation ([NAT](/NAT)) on the Pod IP addresses. 

The pods can **directly** connect to each other using their native IP addresses.

Every new Pod has a new address:
- [GKE](/techstack/k8s/GKE.md) ([kubernetes](/kubernetes)) has a answer to find the Pod's IP -> [service](/techstack/gcp/service.md)