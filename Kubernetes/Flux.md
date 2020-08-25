## Flux

### GitOps Requirements
- A **Git Repo** that defines cluster desired state.
- A **Container Registry** where your CI system pushes immutable images.
- A **CD Process** that:
	- Watches changes in the **Git Repo** and applies them to the cluster.
	- Watches the **Container Registry** for new image releases and updates workload definitions in Git according to predefined upgrade policies. From the K8s cluster, Flux will take the image secret and use it to connect to the Container Registry. It caches images and tags 

### Flux Flow
![Flux Flow](https://i.ibb.co/pZdWPkc/Screen-Shot-2020-08-25-at-9-40-55.png)
1. Pulls **Git Repo**.
2. Watches 

![Flux Flow](https://i.ibb.co/YhFnChf/Screen-Shot-2020-08-25-at-9-46-14.png)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3ODcxMjI3ODQsMjA5MDAzNDldfQ==
-->