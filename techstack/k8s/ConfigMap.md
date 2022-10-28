#k8s #kubernetes 

ConfigMaps promote [[Twelve-Factor]]-ness

```sh
$ kubectl create configmap [NAME] [DATA]
```

#### Example
```sh
# from cmd line
kubectl create configmap demo --from-literal=lab.difficulty=easy --from-literal=lab.resolution=high

# from file
kubectl create configmap demo --from-file=[PATH/FILE]
```

Or by using a manifest!

[[pod]]s using the ConfigMap as
- [[environment variable]]
- [[pod]] commands
- [[volume]]
```yaml
[...]
kind: Pod
spec:
	containers:
	- name: demo-container
	  image: k8s.gcr.io/busybox
	  volumeMounts:
		- name: config-volume
			mountPath: /etc/config
	volumes:
	- name: config-volume
		configMap:
			name: demo
```