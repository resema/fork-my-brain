#gcp #cloud 

Use a [global load balancer](/global%20load%20balancer) to provide access to services deployed in multiple [region](/region)s.

Use a [regional load balancer](/regional%20load%20balancer) to provide access to services deployed in a single [region](/region).

If your load balancers have public [IP](/IP)s, secure them with [SSL](/SSL)

- HTTP(S) load balancing
- TCP load balancing
- UDP load balancing

### Server Load Balancing
- Advantages: [scalability](/architecture/requirements/scalability.md), [availability](/availability), [security](/security), [service quality](/service%20quality)

- [stateless](/stateless) load balancing:
	- uses [hash](/hash) function
		- [IP](/IP) hash
	- advantages
		- easy to implement
		- works for any type of IP-based application/network traffic

- [stateful](/stateful) load balancing
	- load balancer must know protocol semantics to recognize session initiation and termination
	- [session persistence](/session%20persistence)