#k8s #kubernetes 

StatefulSets are designed for [[stateful]] application.

Each [[pod]] in a StatefulSet maintains a [[persistent identity]]
- ordinal index
- stable hostname
- stably identified storage

Deployment, scaling, and updates are ordered using the [[ordinal index]] of the [[pod]]s within a StatefulSet

StatefulSet name _demo_ launches 3 [[replica]]s:
- launches [[pod]]s sequentially named
- scaling and rolling updates happen in reverse order

[[Pod Management Policy]] 
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