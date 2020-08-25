## Flux
### Source: [https://docs.fluxcd.io/en/1.20.1/faq/](https://docs.fluxcd.io/en/1.20.1/faq/) [https://www.youtube.com/watch?v=u8usjpl3jWM](https://www.youtube.com/watch?v=u8usjpl3jWM)

### What does Flux do?
- Continuous Delivery (CD) Tool.
- Goal: To *automate deployment* to **Kubernetes**.
- Uses 2 things: **(1) YAML Configuration** (from Git Repo) and **(2) Container Images** (from Container Registry).
- Needs a **git ssh key** to access your Git Repo (for write access), saved in K8s secret.
- Can be installed using Helm.
- Supports Kustomize. If Helm doesn't support a certain customization, you can patch with Kustomize after running Helm template.
![Simple Flux Flow](https://i.ibb.co/pZdWPkc/Screen-Shot-2020-08-25-at-9-40-55.png)

### What is GitOps?
- With GitOps, we replace commands such as `kubectl apply`, `kubectl set image`, or `helm upgrade` and so on with `git push`. 
- For example, we push to a  Git Repo using `git push`. Flux will sync to the Git Repo and communicate with the Kubernetes API using `kubectl` commands automatically.
- So, we don't need to run the `kubectl` commands, we only need to `git push`.
- With this, you can see commit logs and revert commits.

### GitOps Requirements
- A **Git Repo** that defines your cluster desired state. Flux *synchronizes* the repo with your Kubernetes cluster.
- A **Container Registry** where your CI system pushes immutable images. Flux *monitors* the registry for new images and updates your Git Repo.
- A **CD Process** that:
	- Watches changes in the **Git Repo** and applies them to the cluster. Flux does this in 5 minute intervals, but it can be set.
	- Watches the **Container Registry** for new image releases. Flux does this by taking the image secret of the K8s cluster and use it to connect to the Container Registry. It caches images and tags (metadata; to see the version of the image, etc.) and saves it to **Memcached**.
	- Lastly, Flux updates the YAML configurations in Git according to predefined upgrade policies. This is not an automatic process, you need to run a Flux command or make an API call to do this.
![Full Flux Flow](https://i.ibb.co/YhFnChf/Screen-Shot-2020-08-25-at-9-46-14.png)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE5OTExMDc2MzAsLTE1NTQ5MTAxODEsLT
E3NTk4ODQ5OTIsMTc2MzcwMDgsMTAyODg5MzAxMiwyMDkwMDM0
OV19
-->