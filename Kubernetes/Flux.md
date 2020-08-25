## Flux

### GitOps Requirements
- A **Git Repo** that defines cluster desired state.
- A **Container Registry** where your CI system pushes immutable images.
- A **CD Process** that:
	- Watches changes in the **Git Repo** and applies them to the cluster.
	- Watches the **Container Registry** for new image releases and updates workload definitions in Git according to predefined upgrade policies.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjA5MDAzNDldfQ==
-->