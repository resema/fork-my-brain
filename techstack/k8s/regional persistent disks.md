#k8s #kubernetes #storage 

Another [Storage](/techstack/gcp/Storage.md) is the regional persistent disks replicate the volume in each region. Provides therefore a kind of backup if one fails.

```yaml
apiVersion: storage.k8s.io/v1
kind: StorageClass
metadata:
	name: ssd
provisioner: kubernetes.io/gce-pd
parameters:
	type: pd-ssd
	replication-type: regional-pd
	zones: us-central1-a, us-central1-b
```