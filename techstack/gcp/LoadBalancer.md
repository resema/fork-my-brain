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

- builds upon [[nodePort]] and therefore also [[clusterIP]]