#gcp #cloud 

Use a [[global load balancer]] to provide access to services deployed in multiple [[region]]s.

Use a [[regional load balancer]] to provide access to services deployed in a single [[region]].

If your load balancers have public [[IP]]s, secure them with [[SSL]]

- HTTP(S) load balancing
- TCP load balancing
- UDP load balancing

### Server Load Balancing
- Advantages: [[scalability]], [[availability]], [[security]], [[service quality]]

- [[stateless]] load balancing:
	- uses [[hash]] function
		- [[IP]] hash
	- advantages
		- easy to implement
		- works for any type of IP-based application/network traffic

- [[stateful]] load balancing
	- load balancer must know protocol semantics to recognize session initiation and termination
	- [[session persistence]]