#gcp #cloud

A Sevice is issued a static virtual [[IP address]]
- circumvents the issue that every [[pod]] has a new [[IP address]]
- [[IP address]] are defined by [[IP address ranges]] per [[cluster]]
	- the [[pod]]s have endpoints for communication with the service base on [[label]]s
- [[environment variable]]s for service discovery
	- [[pod]] sees only the [[environment variable]]s which where set during its start
	- changing effect only visible after re-start of [[pod]]
- an alternativ is [[kube-dns]]