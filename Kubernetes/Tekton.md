## Tekton

### Source: [https://www.youtube.com/watch?v=TQJ_pdTxZr0](https://www.youtube.com/watch?v=TQJ_pdTxZr0) & [https://www.inovex.de/blog/spinnaker-vs-argo-cd-vs-tekton-vs-jenkins-x/](https://www.inovex.de/blog/spinnaker-vs-argo-cd-vs-tekton-vs-jenkins-x/) & [https://www.youtube.com/watch?v=-ji5Z0qJmJs](https://www.youtube.com/watch?v=-ji5Z0qJmJs)

### What does Cloud Native mean?
- Opensource.
- Microservice in containers.
- **Containers** that are dynamically orchestrated.
- Easily scale-in/out.

### CI/CD
- Code is **built, tested, deployed.**
- Determines what code can be merged to what branch.
- Get my code to source to production as quickly and securely as possible.
<img alt="CI/CD Example" src="https://i.ibb.co/tKZXXRz/Screen-Shot-2020-08-25-at-14-58-04.png" width="600px" height="330px" />

### Tekton
- Tekton is a shared set of open source Cloud Native building blocks for CI/CD system. Even though Tekton runs on Kubernetes, it targets on any platform, language, and framework.
- Tekton just provides a framework for executing actions.
- Started on Kubernetes Knative project. People can build images on Kubernetes, but wanted to run tests on those images and define more complex pipelines.

### Tekton Pipelines
- Cloud native components for defining CI/CD pipelines.
- Implemented using Kubernetes Custom Resource Definition (CRD).
- Kubernetes resources: Pods, Services, Deployments, but CRD can define a new resource and create binaries called controllers that can act upon the new resource.
- **Steps:** Existing type: `Kubernetes Container Spec`. Steps specify image, shell commands, or arguments. Steps inside one Task share a Pod for easy communication.
<img alt="Steps" src="https://i.ibb.co/q9qfB31/Screen-Shot-2020-08-25-at-17-11-04.png" width="600px" height="300px" />

- 5 New Custom Resources (CRD) provided by Tekton:
	- **Task:** Made up of **Steps**, run sequentially on same K8s node. Runs as a pod. Can specify input and output (using parameters or PipelineResources defined in the task YAML file).
	- **Pipelines:** Made up of **Tasks** . You can define order of tasks, run sequentially or concurrently, or create own task graph (using keywords like `runAfter`). Tasks can run in multiple nodes. Can pass input from one task to next task. In the below example, we group faster tasks like linting and unit tests, and group slower tasks to run concurrently. This speeds up the pipeline speed.
	- **TaskRun** and **PipelineRun**: Invokes **Tasks** and **Pipelines**.
	- **PipelineResources:** There are 4 types, including **Git, Image, Storage and Cluster**. These can be used to reference a **Git Repo**, **Container Registry**, etc. Using runtime information, we can run pipelines against different stages (ex. prod, stg), pull requests, or a different infrastructure. 

### Example YAML Files
<img alt="Task Input and Outputs" src="https://i.ibb.co/qmQWLxZ/Screen-Shot-2020-08-25-at-16-55-12.png" width="600px" height="300px" />
<img alt="Tekton Pipelines: example" src="https://i.ibb.co/bRDNz4L/Screen-Shot-2020-08-25-at-15-47-07.png" width="600px" height="280px" />
<img alt="TaskRun" src="https://i.ibb.co/GWKknHh/Screen-Shot-2020-08-25-at-17-13-32.png" width="600px" height="330px" />
	<img alt="PipelineRun" src="https://i.ibb.co/YQXT8ZC/Screen-Shot-2020-08-25-at-17-13-20.png" width="600px" height="310px" />
	<img alt="PipelineResource" src="https://i.ibb.co/wrQ9kKS/Screen-Shot-2020-08-25-at-16-57-43.png" width="600px" height="310px" />
	<img alt="CI/CD Pipeline" src="https://i.ibb.co/Twn8FcZ/Screen-Shot-2020-08-25-at-16-52-56.png" width="600px" height="310px" />

### High-level Flow of Tekton
1. User interact with Kubernetes to create Task or Pipelines, which are stored in Kubernetes.
2. When user wants to run, users create Task Run or PipelineRun. Picked up by controllers, and these controllers create `pods`.
<img alt="Tekton Pipelines: architecture" src="https://i.ibb.co/ySJ4s7N/Screen-Shot-2020-08-25-at-16-14-20.png" width="600px" height="320px" />

### Example Task/Pipeline Flow
1. **Task 1: Build Task** -> Pulls code from Git Repo, builds a container images, pushes the image to a Container Registry.
<img alt="Build Task" src="https://i.ibb.co/4TXNYZT/Screen-Shot-2020-08-25-at-17-03-51.png" width="600px" height="315px" />
2. **Task 2: Deployment Task** -> Takes the deployment manifest and create the deployment. 
<img alt="Deployment Task" src="https://i.ibb.co/nnS7ft6/Screen-Shot-2020-08-25-at-17-03-42.png" width="600px" height="315px" />
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTcxOTg2ODc5MiwtMTg1NDM4MDU3MCw5OT
UxMjcwNjksLTYwMzE2MTQ3MSwtMTI1NzAwMTg3OSwtMTAzNzI3
OTc2OCwtMTYyNjI2MTM2NywxNDgyOTk5MDI1LC04NjYwOTM2MT
ksLTEyNzI2OTUwNjEsMTMxNTI5NjcxOCwzMDU1NzU2NCwtNzcz
MDkyOTE3XX0=
-->