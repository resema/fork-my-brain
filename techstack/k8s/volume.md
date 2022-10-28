#k8s #kubernetes #storage

- are a directory which is accessible to all of the [[container]]s in a [[pod]]
- some volumes are [[ephemeral]]
- some volumes are [[persistent]]
- volumes allow [[container]]s within a [[pod]] to share data between [[VM]]

### Using [[persistent volume]] and [[PersistentVolumeClaim]]

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: demo-pod
spec:
  containers:
  - name: demo-container
    image: gcr.io/hello-app:1.0
    volumeMounts:
    - mountPath: /demo-pod
      name: pd-volume
  volumes:
  - name: pd-volume
    PersistentVolumeClaim:
      claimName: pd-volume-claim
```

```yaml
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: pd-volume-claim
spec:
  storageClassName: "standard"
  accessModes:
  - ReadWriteOnce:
    resources:
      requests:
        storage: 100G
```