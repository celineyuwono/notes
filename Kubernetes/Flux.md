## Flux
Source: [https://docs.fluxcd.io/en/1.20.1/faq/](https://docs.fluxcd.io/en/1.20.1/faq/)
### What does it do?
- Automates Deployment.
- Uses **Configuration** (from **Git Repo**) and **Container Images** (from **Container Registry**) to automate deployment to **Kubernetes**.

### GitOps Requirements
- A **Git Repo** that defines cluster desired state. Flux *synchronizes* the repo with your Kubernetes cluster.
- A **Container Registry** where your CI system pushes immutable images. Flux *monitors* the registry for new images and updates your Git Repo.
- A **CD Process** that:
	- Watches changes in the **Git Repo** and applies them to the cluster. Flux does this in 5 minute intervals, but it can be set.
	- Watches the **Container Registry** for new image releases and updates workload definitions in Git according to predefined upgrade policies. From the K8s cluster, Flux will take the image secret and use it to connect to the Container Registry. It caches images and tags (metadata; to see the version of the image, etc.) and saves it to **Memcached**.

### Flux Flow
![Flux Flow](https://i.ibb.co/pZdWPkc/Screen-Shot-2020-08-25-at-9-40-55.png)
1. Pulls **Git Repo**.
2. Watches 

![Flux Flow](https://i.ibb.co/YhFnChf/Screen-Shot-2020-08-25-at-9-46-14.png)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQyMzQwMDk4OSwyMDkwMDM0OV19
-->