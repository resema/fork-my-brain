#architecture #quality #requirement 

A service is said to be scalable if when we increase the resources in a system, it results in increased [[performance gain|performance]] in a manner proportial to resources added.
- [[vertical scaling]] (scale up)
	- increase [[performance gain|performance]] by adding resources
	- examples: increase RAM, adding CPU, others
- [[horizontal scaling]] (scale out)
	- no limits (from the hardware point of view)
	- increasing the [[performance gain|performance]] of a system by adding additional computers / [[node]]s
	- efficiency, however, strongly depends on the implementation of a software

#### Types of Scalability
- [[load scalability]]
	- constant system behaviour over larger load ranges
- [[spatial scalability]]
	- memory requirements do not increase to an unacceptably high level as the number of elements grows
- [[temporal-spatial scalability]]
	- increasing the number of objects does not significantly affect its performance
- [[structural scalability]]
	- implementation of the system does not significantly hinder the increase of the number of objects

#### Pay attention to!
- does not improve [[performance gain|performance]]
	- increases complexity and reduces [[performance gain|performance]]
	- is slower in single-user mode
	- still have to pay attention to [[performance gain|performance]] :)
- can improve availability and resilience
	- [[horizontal scaling]]
	- synchronize status information