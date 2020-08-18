## Kubernetes Volumes

### Source URL: [https://www.youtube.com/watch?v=0swOh5C3OVM&list=PLy7NrYWoggjwPggqtFsI_zMAwvG0SqYCb&index=26](https://www.youtube.com/watch?v=0swOh5C3OVM&list=PLy7NrYWoggjwPggqtFsI_zMAwvG0SqYCb&index=26)

![Persist Data in Kubernetes](https://i.ibb.co/G5DkKDM/Screen-Shot-2020-08-18-at-10-09-05.png)

### Things to Pay Attention to...
- You will need to configure the Persistent Volumes yourself. 
- Things to pay attention to:
	- Needs storage that don’t depend on pod life cycle. Read where the previous one dies off.
	- Storage must be available on all nodes.
	- Needs storage that survive even in whole cluster fails.

### What are Persistent Volumes (PV)?
- A Persistent Volume is like a cluster resource like RAM, CPU. It is created like YAML File `kind: PersistentVolume`. It needs actual physical storage that you can set.
- Where does this storage comes from and who makes it available to the cluster?
	- Kubernetes doesn’t care about actual storage, so we have to decide and take care of it ourselves. Kubernetes only created the Persistent Volume component.
	- Therefore, storage is an external plugin to the cluster.
	
![YAML File Example](https://i.ibb.co/y6ytSxy/Screen-Shot-2020-08-18-at-10-09-12.png)

### How to Configure PVs
- Persistent volumes are **not** namespaced.
- There are local vs remote volumes.
- **Kubernetes Roles:**
	- **Kubernetes Admin** sets up and maintain cluster.
	- **Kubernetes User** deploys application in cluster.
- Kubernetes Administrator needs to configure actual storage (ex. Make sure nfs is there, configure cloud storage for PV to use, and then create PV components from storage backends).
- Kubenetes Developer needs to configure a `kind: PersistentVolumeClaim (PVC)` YAML file to use the PV. Then in the `kind: Pod` YAML file, specify the `PersistentVolumeClaim`. So, only specified nodes have access to the PV.
- PVC must exist in the same namespace as pod using claim.
- Volume is mounted to pod, then mounted to containers.

### Volume Types
- Two local volume types: **ConfigMap** (maps url to IP) and **Secret** (base64 contain user credentials). These are not created via PV or PVC, but are own components and created and managed by Kubernetes itself.
- Create a ConfigMap or Secret component and mount it in a Pod.

### Storage Class (SC)
- SC provisions PV dynamically when PVC claims it. Created using YAML File `kind: StorageClass`. Specify provisioner (ex. `provisioner: kubernetes.io/ws-ebs`). Kubernetes provides provisioners (internal) but external is also possible. Storage backend is specified here.
- If we use Storage Class, this will be the flow: 
	1. Pod claims storage via PVC.
	2. PVC requests SC.
	3. SC will provision or create PV that meets the needs of the claim using provisioner from actual storage backend.

### Comparison with Docker Volumes
- When a container writes to its file system it gets replicated on the Host File System directory and vice versa.

![What is Docker Volume?](https://i.ibb.co/54cp64X/Screen-Shot-2020-08-18-at-10-42-14.png)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTUzMDYzNDE5N119
-->