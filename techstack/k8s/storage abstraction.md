#gcp #kubernetes #cloud #k8s 

- [[volume]]
- [[persistent volume]]
	- [[regional persistent disks]]
		
### Ephemeral volume types
- shares [[pod]]'s lifecycle
- [[ConfigMap]] can be reference in a volume
- [[Secret]] stores sensitive info, such as passwords
	- never written to non volatile storage
- [[downwardAPI]] makes data about [[pod]]s data available to [[techstack/gcp/container|container]]s

All of those four a created by [[emtpyDir]] volumes, which is first created when a [[pod]] is assigned to a [[node]].

### Different Access Modes
- `ReadWriteOnce`
- `ReadOnlyMany`
- `ReadWriteMany`

### Attention
The [[GKE]] storage is a separate thing from [[GCP]] storages, such as buckets.