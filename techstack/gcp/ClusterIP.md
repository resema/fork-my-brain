#gcp #cloud #ingress

A ClusterIP service has a static [[IP address]]. This or [[NodePort]] are needed for [[Ingress]]es. A [[service]] with type ClusterIP is only accessible from within the [[cluster]].

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