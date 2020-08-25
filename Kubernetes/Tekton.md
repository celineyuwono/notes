## Tekton

### Tekton Pipeline

Installing Tekton Pipelines to your cluster introduces five new Custom Resources: Tasks, Pipelines, TaskRuns, PipelineRuns and PipelineResources. Tasks contain steps (which are essentially shell commands) and can be executed by TaskRuns. Pipelines consist of multiple Tasks and are executed by PipelineRuns. To share resources between different Tasks, PipelineResources can be used. Tekton just provides a framework for executing actions in a defined, acyclic way. Its power comes from the ability to execute whatever command in whatever container on a per-step basis. Steps inside one Task share a Pod for easy communication. With keywords like “runAfter”, you control precisely the order of the Tasks to run in.

Currently, Tekton has four different kinds of PipelineResources: Git, Image, Storage and Cluster. These can be used to reference a code repository, a container image to either be built or loaded, to access stored files and to manage another Kubernetes cluster. The latter allows Tekton Pipelines to not only manipulate the Kubernetes cluster it was deployed to, but any cluster it gets handed as a resource.

### Cloud Native
- Opensource.
- Microservice in containers.
- **Containers** that are dynamically orchestrated.
- Easily scale-in/out

### CI/CD
- Code is **built, tested, deployed.**
- CI determines what code can be merged to what branch.
- Get my code to source to production as quickly and securely as possible!
![CI/CD Example](https://i.ibb.co/tKZXXRz/Screen-Shot-2020-08-25-at-14-58-04.png)

### Tekton
- Tekton is a shared set of open source Cloud Native building blocks for CI/CD system. Even though Tekton runs on Kubernetes, it targets on any platform, language, and framework.
- Started on Kubernetes Knative project. People can build images on Kubernetes, but wanted to run tests on those images and define more complex pipelines.

### Tekton Pipelines
- Cloud native components for defining CI/CD pipelines.
- Implemented using Kubernetes Custom Resource Definition (CRD).
- Kubernetes resources: Pods, Services, Deployments, but CRD can define a new resource and create binaries called controllers that can act upon the new resource.
- Step: Kubernetes Container Spec, specify image and everything you need to run it (ex. ENV var, volumes used).
- Types of Tekton CRD:
	- **Task:** Combine `Steps`, run sequentially on same K8s node.
	- **Pipelines:** Combine `Tasks` . You can define order of tasks, run sequentially or concurrently, or create own task graph. Tasks can run in multiple nodes. Can pass input from one task to next task. In the below example, we group faster tasks like linting and unit tests, and group slower tasks to run concurrently. This speeds up the pipeline speed.
![Tekton Pipelines: example](https://i.ibb.co/bRDNz4L/Screen-Shot-2020-08-25-at-15-47-07.png)
	- **Pipeline Run** and **Task Run**: Run Pipelines and Tasks multiple times. Needs runtime information: **Git Repo** and **Container Registry**.
	- **Pipeline Resources:** d

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEzODMyNzk1NjMsMzA1NTc1NjQsLTc3Mz
A5MjkxN119
-->