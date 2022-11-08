#gcp #cloud 

LoadBalancer service can be used to expose a [[service]] to resources outside the [[cluster]].

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

- builds upon [[NodePort]] and therefore also [[ClusterIP]]

#### Container-Native load balancing
- new feature in [[GKE]]
	- traffic is directed to the [[pod]]s directly instead of to the [[node]]s
	- requires [[GKE]] to operate in [[VPC]] native mode
		- uses a data model called [[Network Endpoint Groups|NEG]]
			- every connection is made between the [[LoadBalancer]] and the [[pod]]