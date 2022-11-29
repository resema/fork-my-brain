#gcp #cloud 

LoadBalancer service can be used to expose a [service](/techstack/gcp/service.md) to resources outside the [cluster](/cluster).

```yaml
[...]
spec:
	type: LoadBalancer
	selector:
			app: external
		ports:
			- protocol: TCP
			port: 80
			  targetPort: 9376
```

- builds upon [nodePort](/techstack/gcp/nodePort.md) and therefore also [ClusterIP](/techstack/gcp/ClusterIP.md)

#### Container-Native load balancing
- new feature in [GKE](/techstack/k8s/GKE.md)
	- traffic is directed to the [pod](/techstack/gcp/pod.md)s directly instead of to the [Node](/techstack/gcp/Node.md)s
	- requires [GKE](/techstack/k8s/GKE.md) to operate in [VPC](/techstack/gcp/VPC.md) native mode
		- uses a data model called [NEG](/Network%20Endpoint%20Groups)
			- every connection is made between the [LoadBalancer](/techstack/k8s/LoadBalancer.md) and the [pod](/techstack/gcp/pod.md)