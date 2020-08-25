## Tekton

### Source: [https://www.youtube.com/watch?v=TQJ_pdTxZr0](https://www.youtube.com/watch?v=TQJ_pdTxZr0) [https://www.inovex.de/blog/spinnaker-vs-argo-cd-vs-tekton-vs-jenkins-x/](https://www.inovex.de/blog/spinnaker-vs-argo-cd-vs-tekton-vs-jenkins-x/) [https://www.youtube.com/watch?v=-ji5Z0qJmJs](https://www.youtube.com/watch?v=-ji5Z0qJmJs)

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
- **Steps:** Existing type: `Kubernetes Container Spec`. Steps specify image, shell commands, or arguments. Steps inside one Task share a Pod for easy communication.
- 5 New Custom Resources (CRD) provided by Tekton:
![Tekton Components](https://i.ibb.co/82JmRcM/Screen-Shot-2020-08-25-at-15-55-22.png)
	- **Task:** Made up of **Steps**, run sequentially on same K8s node. Runs as a pod. Can specify input and output (using parameters or PipelineResources defined in the task YAML file).
	![Screen-Shot-2020-08-25-at-16-55-12](https://i.ibb.co/qmQWLxZ/Screen-Shot-2020-08-25-at-16-55-12.png)
	- **Pipelines:** Made up of **Tasks** . You can define order of tasks, run sequentially or concurrently, or create own task graph (using keywords like `runAfter`). Tasks can run in multiple nodes. Can pass input from one task to next task. In the below example, we group faster tasks like linting and unit tests, and group slower tasks to run concurrently. This speeds up the pipeline speed.
![Tekton Pipelines: example](https://i.ibb.co/bRDNz4L/Screen-Shot-2020-08-25-at-15-47-07.png)
	- **PipelineRun** and **TaskRun**: Invokes **Pipelines** and **Tasks**.
	- **PipelineResources:** There are 4 types, including **Git, Image, Storage and Cluster**. These can be used to reference a **Git Repo** or **Container Registry**. Using runtime information, we can run pipelines against different stages (ex. prod, stg), pull requests, or a different infrastructure. 
	![PipelineResource](https://i.ibb.co/wrQ9kKS/Screen-Shot-2020-08-25-at-16-57-43.png)
	![CI/CD Pipeline](https://i.ibb.co/Twn8FcZ/Screen-Shot-2020-08-25-at-16-52-56.png)

### Flow
1. User interact with Kubernetes to create Task or Pipelines, which are stored in Kubernetes.
2. When user wants to run, users create Task Run or PipelineRun. Picked up by controllers, and these controllers create `pods`.
![](https://i.ibb.co/ySJ4s7N/Screen-Shot-2020-08-25-at-16-14-20.png)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTk2OTI5ODY1NiwtMTAzNzI3OTc2OCwtMT
YyNjI2MTM2NywxNDgyOTk5MDI1LC04NjYwOTM2MTksLTEyNzI2
OTUwNjEsMTMxNTI5NjcxOCwzMDU1NzU2NCwtNzczMDkyOTE3XX
0=
-->