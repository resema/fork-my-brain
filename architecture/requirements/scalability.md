#architecture #quality #requirement 

A service is said to be scalable if when we increase the resources in a system, it results in increased [performance](/architecture/requirements/performance%20gain.md) in a manner proportial to resources added.
- [vertical scaling](/techstack/gcp/vertical%20scaling.md) (scale up)
	- increase [performance](/architecture/requirements/performance%20gain.md) by adding resources
	- examples: increase RAM, adding CPU, others
- [horizontal scaling](/techstack/gcp/horizontal%20scaling.md) (scale out)
	- no limits (from the hardware point of view)
	- increasing the [performance](/architecture/requirements/performance%20gain.md) of a system by adding additional computers / [Node](/techstack/gcp/Node.md)s
	- efficiency, however, strongly depends on the implementation of a software

#### Types of Scalability
- [load scalability](/load%20scalability)
	- constant system behaviour over larger load ranges
- [spatial scalability](/spatial%20scalability)
	- memory requirements do not increase to an unacceptably high level as the number of elements grows
- [temporal-spatial scalability](/temporal-spatial%20scalability)
	- increasing the number of objects does not significantly affect its performance
- [structural scalability](/structural%20scalability)
	- implementation of the system does not significantly hinder the increase of the number of objects

#### Pay attention to!
- does not improve [performance](/architecture/requirements/performance%20gain.md)
	- increases complexity and reduces [performance](/architecture/requirements/performance%20gain.md)
	- is slower in single-user mode
	- still have to pay attention to [performance](/architecture/requirements/performance%20gain.md) :)
- can improve availability and resilience
	- [horizontal scaling](/techstack/gcp/horizontal%20scaling.md)
	- synchronize status information