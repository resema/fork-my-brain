#gcp #cloud

A Sevice is issued a static virtual [IP address](/IP%20address)
- circumvents the issue that every [pod](/techstack/gcp/pod.md) has a new [IP address](/IP%20address)
- [IP address](/IP%20address) are defined by [IP address ranges](/techstack/network/IP%20address%20ranges.md) per [cluster](/cluster)
	- the [pod](/techstack/gcp/pod.md)s have endpoints for communication with the service base on [label](/label)s
- [environment variable](/environment%20variable)s for service discovery
	- [pod](/techstack/gcp/pod.md) sees only the [environment variable](/environment%20variable)s which where set during its start
	- changing effect only visible after re-start of [pod](/techstack/gcp/pod.md)
- an alternativ is [kube-dns](/techstack/gcp/kube-dns.md)