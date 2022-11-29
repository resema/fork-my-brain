#k8s #kubernetes #storage

- are a directory which is accessible to all of the [container](/techstack/gcp/container.md)s in a [pod](/techstack/gcp/pod.md)
- some volumes are [ephemeral](/ephemeral)
- some volumes are [persistent](/persistent)
- volumes allow [container](/techstack/gcp/container.md)s within a [pod](/techstack/gcp/pod.md) to share data between [VM](/VM)

### Using [persistent volume](/techstack/k8s/persistent%20volume.md) and [PersistentVolumeClaim](/PersistentVolumeClaim)

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