#gcp #cloud 

a clusterIP service has a static [[IP address]]

```yaml
apiVersion: v1
kind: Service
metadata:
	name: my-service
spec:
	type: ClusterIP
	selector:
		app: Backend
	ports:
		- protocol: TCP
		  port: 3306
		  targetPort: 6000
```

How does it work?
- defines a static [[IP address]] for the [[service]] `my-service` with a [[port]] `3306`. The backend [[pod]]s have the [[targetPort]] 6000`.`