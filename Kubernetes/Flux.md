## Flux

### GitOps Requirements
- A **Git Repo** that defines cluster desired state.
- A **Container Registry** where your CI system pushes immutable images.
- A **CD Process** that:
	- Watches changes in the **Git Repo** and applies them to the cluster.
	- Watches the **Container Registry** for new image releases and updates workload definitions in Git according to predefined upgrade policies.

### Flux Flow
1. Pulls **Git Repo**.
2. Watches CR
![Flux Flow](https://i.ibb.co/pZdWPkc/Screen-Shot-2020-08-25-at-9-40-55.png)
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTE0Njc1NjkxOSwyMDkwMDM0OV19
-->