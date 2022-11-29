#gcp #cloud #ingress

Useful for internal communication within cluster. Helps to expose a service with port`30100` to external [LoadBalancer](/techstack/k8s/LoadBalancer.md)

```yaml
apiVersion: v1
kind: Service
metadata:
	name: my-service
spec:
	type: NodePort
	selector:
		app: Backend
	ports:
		- protocol: TCP
		  nodePort: 30100
		  port: 3306
		  targetPort: 6000
```

How does it work?
- [ClusterIP](/techstack/gcp/ClusterIP.md) service is automatically created while creating nodePort