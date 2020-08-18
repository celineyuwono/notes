## Kubernetes Volumes

### Source URL: [https://www.youtube.com/watch?v=0swOh5C3OVM&list=PLy7NrYWoggjwPggqtFsI_zMAwvG0SqYCb&index=26](https://www.youtube.com/watch?v=0swOh5C3OVM&list=PLy7NrYWoggjwPggqtFsI_zMAwvG0SqYCb&index=26)

screenshot

### Configuring Volumes
- You will need to configure the volumes yourself. 
- Things to pay attention to:
	- Needs storage that don’t depend on pod life cycle. Read where the previous one dies off.
	- Storage must be available on all nodes.
	- Needs storage that survive even in whole cluster fails.

### Persistent Volumes
- Persistent Volume is like a cluster resource like RAM, CPU. It is created like YAML File (kind: PersistentVolume). Needs actual physical storage that you can set.
	- Where does this storage comes from and who makes it available to the cluster?
	- Kubernetes doesn’t care about actual storage, so we have to decide and take care of it ourselves. Kubernetes only created the Persistent Volume component.
	- Therefore, storage is an external plugin to the cluster.
	- SCREENSHOT
	- Persistent volumes are not namespaced.
	- There are local vs remote volumes.
	- Kubernetes Roles:
		- Kubernetes Admin sets up and maintain cluster.
		- Kubernetes User deploys application in cluster.
	- Kubernetes Administrator needs to configure actual storage. Example: Make sure nfs is there, configure cloud storage for PV to use, and then create PV components from storage backends.
	- Kubenetes Developer needs to configure a kind: PersistentVolumeClaim (PVC) YAML file to use the PV. Then in the kind: Pod YAML file, specify the PersistentVolumeClaim. So, only specified nodes have access to the PV.
	- PVC must exist in the same namespace as pod using claim.
	- Volume is mounted to pod, then mounted to containers.
	- Two local volume types: **ConfigMap** (maps url to IP) and **Secret** (base64 contain user credentials). Not created via PV or PVC, but own components and created and managed by Kubernetes itself.
		- Create ConfigMap or Secret component and mount in Pod.

<![if !supportLists]>o <![endif]>Storage Class: Provisions PV dynamically when PVC claims it. Created using YAML File (kind: StorageClass). Specify provisioner, example: provisioner: kubernetes.io/ws-ebs. Kubernetes provides provisioners (internal) but external is also possible. Storage backend is specified here.

<![if !supportLists]>o <![endif]>If we use Storage Class, this will be the flow: Pod claims storage via PVC -> PVC requests SC -> SC will provision or create PV that meets the needs of the claim using provisioner from actual storage backend.
<!--stackedit_data:
eyJoaXN0b3J5IjpbNjA0MTI2MDM1LDczMDk5ODExNl19
-->