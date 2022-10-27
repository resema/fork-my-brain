#k8s #kubernetes #storage 

- manage durable storage in a [[cluster]]
- are independent of the [[pod]]'s lifecycle
- provisioned dynamically through [[PersistentVolumeClaim]] or explicitly create by a [[cluster]] admin
- abstracts storage provisioning from storage consumption

#### Two job roles
- allows [[cluster]] administrator to provision and maintain storage
- developers can claim provisioned storage for app consumption

### PersistentVolume abstraction
- has two components
	- `PersistentVolume (PV)` 
		- independent of [[pod]]'s lifcyle
		- managed by [[kubernetes]]
		- manually or dynamically provisioned
		- persistend disks are used by [[GKE]] as PersistentVolumes
	- `PersistenVolumeClaim (PVC)`
		- [[pod]] uses `PVClaim` to uses a persistent volume 