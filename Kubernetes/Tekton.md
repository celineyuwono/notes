## Tekton

### Tekton Pipeline

Currently, Tekton has four different kinds of PipelineResources: Git, Image, Storage and Cluster. These can be used to reference a code repository, a container image to either be built or loaded, to access stored files and to manage another Kubernetes cluster. The latter allows Tekton Pipelines to not only manipulate the Kubernetes cluster it was deployed to, but any cluster it gets handed as a resource.

### What does Cloud Native mean?
- Opensource.
- Microservice in containers.
- **Containers** that are dynamically orchestrated.
- Easily scale-in/out.

### CI/CD
- Code is **built, tested, deployed.**
- Determines what code can be merged to what branch.
- Get my code to source to production as quickly and securely as possible!
![CI/CD Example](https://i.ibb.co/tKZXXRz/Screen-Shot-2020-08-25-at-14-58-04.png)

### Tekton
- Tekton is a shared set of open source Cloud Native building blocks for CI/CD system. Even though Tekton runs on Kubernetes, it targets on any platform, language, and framework.
- Tekton just provides a framework for executing actions.
- Started on Kubernetes Knative project. People can build images on Kubernetes, but wanted to run tests on those images and define more complex pipelines.

### Tekton Pipelines
- Cloud native components for defining CI/CD pipelines.
- Implemented using Kubernetes Custom Resource Definition (CRD).
- Kubernetes resources: Pods, Services, Deployments, but CRD can define a new resource and create binaries called controllers that can act upon the new resource.
- **Steps:** Kubernetes Container Spec, specify image and everything you need to run it (ex. ENV var, volumes used). Steps are essentially shell commands. Steps inside one Task share a Pod for easy communication.
- 5 New Custom Resources (CRD) provided by Tekton:
	- **Task:** Made up of **Steps**, run sequentially on same K8s node. 
	- **Pipelines:** Made up of **Tasks** . You can define order of tasks, run sequentially or concurrently, or create own task graph (using keywords like `runAfter`). Tasks can run in multiple nodes. Can pass input from one task to next task. In the below example, we group faster tasks like linting and unit tests, and group slower tasks to run concurrently. This speeds up the pipeline speed.
![Tekton Pipelines: example](https://i.ibb.co/bRDNz4L/Screen-Shot-2020-08-25-at-15-47-07.png)
	- **Pipeline Run** and **Task Run**: Invoke **Pipelines** and **Tasks** (because they usually need to be invoked multiple times).
	- **Pipeline Resources:** Share resources between different **Tasks** and *provides runtime information* like **Git Repo** and **Container Registry**. Using runtime information, we can run pipelines against different stages (ex: 
![Tekton Components](https://i.ibb.co/82JmRcM/Screen-Shot-2020-08-25-at-15-55-22.png)

### Pipeline Resources
- By decoupling runtime information, we can:
	- Run pipeline against different stages: 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTI4NDQzNjM3MywtMTI3MjY5NTA2MSwxMz
E1Mjk2NzE4LDMwNTU3NTY0LC03NzMwOTI5MTddfQ==
-->