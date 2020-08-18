## Kubernetes Volumes

### Source URL: [https://www.youtube.com/watch?v=0swOh5C3OVM&list=PLy7NrYWoggjwPggqtFsI_zMAwvG0SqYCb&index=26](https://www.youtube.com/watch?v=0swOh5C3OVM&list=PLy7NrYWoggjwPggqtFsI_zMAwvG0SqYCb&index=26)

screenshot

- You need to configure yourself.
- Need storage that don’t depend on pod life cycle. Read where the previous one dies off.
	- Storage must be available on all nodes.
	- Need storage that survive even in whole cluster fails.
- Persistent Volume is like a cluster resource like RAM, CPU. It is created like YAML File (kind: PersistentVolume). Needs actual physical storage that you can set.
	- Where does this storage comes from and who makes it available to the cluster?
	- Kubernetes doesn’t care about actual storage, so we have to decide and take care of it ourselves. Kubernetes only created the Persistent Volume component.

<![if !supportLists]>o <![endif]>Therefore, storage is an external plugin to the cluster.

<![if !supportLists]>o <![endif]><![if !vml]>![A close up of text on a black background

Description automatically generated](file:////Users/ts-celine.yuwono/Library/Group%20Containers/UBF8T346G9.Office/TemporaryItems/msohtmlclip/clip_image002.png)<![endif]>We configure storage using YAML file. (Or take from internet).

<![if !supportLists]>o <![endif]>Persistent volumes are not namespaced.

<![if !supportLists]>o <![endif]>Local vs remote volumes.

<![if !supportLists]>o <![endif]>Kubernetes Roles:

<![if !supportLists]>§ <![endif]>Kubernetes Admin sets up and maintain cluster.

<![if !supportLists]>§ <![endif]>Kubernetes User deploys application in cluster.

<![if !supportLists]>o <![endif]>Kubernetes Administrator needs to configure actual storage. Example: Make sure nfs is there, configure cloud storage for PV to use, and then create PV components from storage backends.

<![if !supportLists]>o <![endif]>Kubenetes Developer needs to configure a kind: PersistentVolumeClaim (PVC) YAML file to use the PV. Then in the kind: Pod YAML file, specify the PersistentVolumeClaim. So, only specified nodes have access to the PV.

<![if !supportLists]>o <![endif]>PVC must exist in the same namespace as pod using claim.

<![if !supportLists]>o <![endif]>Volume is mounted to pod, then mounted to containers.

<![if !supportLists]>o <![endif]>Two local volume types: ConfigMap (maps url to IP) and Secret (base64 contain user credentials). Not created via PV or PVC, but own components and created and managed by Kubernetes itself.

<![if !supportLists]>§ <![endif]>Create ConfigMap or Secret component and mount in Pod.

<![if !supportLists]>o <![endif]>Storage Class: Provisions PV dynamically when PVC claims it. Created using YAML File (kind: StorageClass). Specify provisioner, example: provisioner: kubernetes.io/ws-ebs. Kubernetes provides provisioners (internal) but external is also possible. Storage backend is specified here.

<![if !supportLists]>o <![endif]>If we use Storage Class, this will be the flow: Pod claims storage via PVC -> PVC requests SC -> SC will provision or create PV that meets the needs of the claim using provisioner from actual storage backend.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIyMjA5ODQzNCw3MzA5OTgxMTZdfQ==
-->