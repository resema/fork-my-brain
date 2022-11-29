#k8s #kubernetes 

StatefulSets are designed for [stateful](/stateful) application.

Each [pod](/techstack/gcp/pod.md) in a StatefulSet maintains a [persistent identity](/persistent%20identity)
- ordinal index
- stable hostname
- stably identified storage

Deployment, scaling, and updates are ordered using the [ordinal index](/ordinal%20index) of the [pod](/techstack/gcp/pod.md)s within a StatefulSet

StatefulSet name _demo_ launches 3 [replica](/replica)s:
- launches [pod](/techstack/gcp/pod.md)s sequentially named
- scaling and rolling updates happen in reverse order

[Pod Management Policy](/Pod%20Management%20Policy) 
- `OrderedReady (default)`
- `parallel`

### Example
```yaml
apiVersion: v1
kind: Service
metadata:
	name: demo-service
	labels:
		app: demo
spec:
	ports:
	- port: 80
		name: web
	clusterIP: None
	selector:
		app: demo
```

```yaml
apiVersion: apps/v1
kind: StatefulSet
metadata:
	name: demo-statefulset
spec:
	selector:
		matchLabels:
			app: demo
	serviceName: demo-service
[...]
```