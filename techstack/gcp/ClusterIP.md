#gcp #cloud #ingress

A ClusterIP service has a static [IP address](/IP%20address). This or [nodePort](/techstack/gcp/nodePort.md) are needed for [Ingress](/techstack/k8s/Ingress.md)es. A [service](/techstack/gcp/service.md) with type ClusterIP is only accessible from within the [cluster](/cluster).

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
- defines a static [IP address](/IP%20address) for the [service](/techstack/gcp/service.md) `my-service` with a [port](/port) `3306`. The backend [pod](/techstack/gcp/pod.md)s have the [targetPort](/targetPort) 6000`.`