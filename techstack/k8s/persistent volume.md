#k8s #kubernetes #storage 

- manage durable storage in a [cluster](/cluster)
- are independent of the [pod](/techstack/gcp/pod.md)'s lifecycle
- provisioned dynamically through [PersistentVolumeClaim](/PersistentVolumeClaim) or explicitly create by a [cluster](/cluster) admin
- abstracts storage provisioning from storage consumption

#### Two job roles
- allows [cluster](/cluster) administrator to provision and maintain storage
- developers can claim provisioned storage for app consumption

### PersistentVolume abstraction
- has two components
	- `PersistentVolume (PV)` 
		- independent of [pod](/techstack/gcp/pod.md)'s lifcyle
		- managed by [kubernetes](/kubernetes)
		- manually or dynamically provisioned
		- persistend disks are used by [GKE](/techstack/k8s/GKE.md) as PersistentVolumes
	- `PersistenVolumeClaim (PVC)`
		- [pod](/techstack/gcp/pod.md) uses `PVClaim` to uses a persistent volume 

### Example
```yaml
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: hello-web-disk
spec:
  accessModes:
    - ReadWriteOnce
  resources:
    requests:
      storage: 30Gi
```

```yaml
kind: Pod
apiVersion: v1
metadata:
  name: pvc-demo-pod
spec:
  containers:
    - name: frontend
      image: nginx
      volumeMounts:
      - mountPath: "/var/www/html"
        name: pvc-demo-volume
  volumes:
    - name: pvc-demo-volume
      persistentVolumeClaim:
        claimName: hello-web-disk
```