## Flux
### Source: [https://docs.fluxcd.io/en/1.20.1/faq/](https://docs.fluxcd.io/en/1.20.1/faq/) [https://www.youtube.com/watch?v=u8usjpl3jWM](https://www.youtube.com/watch?v=u8usjpl3jWM)

### What does Flux do?
- Continuous Delivery (CD) Tool.
- Goal: To *automate deployment* to **Kubernetes**.
- Uses 2 things: **(1) YAML Configuration** (from Git Repo) and **(2) Container Images** (from Container Registry).
- Needs a **git ssh key** to access your Git Repo (for write access), saved in K8s secret.
- Can be installed using Helm.
![Simple Flux Flow](https://i.ibb.co/pZdWPkc/Screen-Shot-2020-08-25-at-9-40-55.png)

### GitOps Requirements
- A **Git Repo** that defines your cluster desired state. Flux *synchronizes* the repo with your Kubernetes cluster.
- A **Container Registry** where your CI system pushes immutable images. Flux *monitors* the registry for new images and updates your Git Repo.
- A **CD Process** that:
	- Watches changes in the **Git Repo** and applies them to the cluster. Flux does this in 5 minute intervals, but it can be set.
	- Watches the **Container Registry** for new image releases. Then, updates workload definitions in Git according to predefined upgrade policies. Flux does this by taking the image secret of the K8s cluster and use it to connect to the Container Registry. It caches images and tags (metadata; to see the version of the image, etc.) and saves it to **Memcached**.
![Full Flux Flow](https://i.ibb.co/YhFnChf/Screen-Shot-2020-08-25-at-9-46-14.png)


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTkxMjY3OTIwMiwyMDkwMDM0OV19
-->