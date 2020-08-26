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

### What is Tekton
- Cloud native components for defining CI/CD pipelines.
- Even though Tekton runs on Kubernetes, it targets on any platform, language, and framework.
- Tekton just provides a framework for executing actions.
- Started on Kubernetes Knative project. People can build images on Kubernetes, but wanted to run tests on those images and define more complex pipelines.

### Tekton 5 New CRD
- Implemented using Kubernetes Custom Resource Definition (CRD).
- Kubernetes resources: Pods, Services, Deployments, but CRD can define a new resource and create binaries called controllers that can act upon the new resource. Basically, extending Kubernetes resources.
- **Steps:** Existing type: `Kubernetes Container Spec`. Steps specify image, shell commands, or arguments. Steps inside one Task share a Pod for easy communication.
<img alt="Steps" src="https://i.ibb.co/q9qfB31/Screen-Shot-2020-08-25-at-17-11-04.png" width="600px" height="300px" />
- 5 New Custom Resources (CRD) provided by Tekton:
	1. **Task:** Made up of **Steps**, run sequentially on same K8s node. Runs as a pod. Can specify input and output (using parameters or PipelineResources defined in the task YAML file).
	2. **Pipeline:** Made up of **Tasks** . You can define order of tasks, run sequentially or concurrently, or create own task graph (using keywords like `runAfter`). 
	3. **TaskRun**: Invokes **Tasks**.
	4. **PipelineRun**: Invokes **Pipeline** 
	5. **PipelineResources:** There are 4 types, including **Git, Image, Storage and Cluster**. These can be used to reference a **Git Repo**, **Container Registry**, etc. Using runtime information, we can run pipelines against different stages (ex. prod, staging), pull requests, or a different infrastructure. 

### Tekton CRD Example YAML Files
1. `kind: Task`

<img alt="Task" src="https://i.ibb.co/qmQWLxZ/Screen-Shot-2020-08-25-at-16-55-12.png" width="600px" height="300px" />

2. `kind: Pipeline`

<img alt="Pipeline" src="https://i.ibb.co/JpPgkhP/Screen-Shot-2020-08-25-at-17-49-28.png" width="600px" height="280px" />

3. `kind: TaskRun`

<img alt="TaskRun" src="https://i.ibb.co/GWKknHh/Screen-Shot-2020-08-25-at-17-13-32.png" width="600px" height="330px" />

4. `kind: PipelineRun`

<img alt="PipelineRun" src="https://i.ibb.co/YQXT8ZC/Screen-Shot-2020-08-25-at-17-13-20.png" width="600px" height="310px" />

5. `kind: PipelineResource`

<img alt="PipelineResource" src="https://i.ibb.co/wrQ9kKS/Screen-Shot-2020-08-25-at-16-57-43.png" width="600px" height="310px" />

### More about Tekton Tasks
<ul>
<li>
Tasks can run in multiple nodes and can pass input to the next task. 
</li>
<img alt="CI/CD Pipeline" src="https://i.ibb.co/Twn8FcZ/Screen-Shot-2020-08-25-at-16-52-56.png" width="600px" height="310px" />
<li>
In the below example, we group faster tasks like linting and unit tests, and group slower tasks to run concurrently. This speeds up the pipeline speed.
</li>
<img alt="Tekton Pipelines: example" src="https://i.ibb.co/bRDNz4L/Screen-Shot-2020-08-25-at-15-47-07.png" width="600px" height="280px" />
</ul>

### Example Task/Pipeline
<ol>
<li><b>Task 1: Build Task</b> -> Pulls code from Git Repo, builds a container images, pushes the image to a Container Registry. </li>
<img alt="Build Task" src="https://i.ibb.co/4TXNYZT/Screen-Shot-2020-08-25-at-17-03-51.png" width="600px" height="315px" />
<li><b>Task 2: Deployment Task</b> -> Takes the deployment manifest and create the deployment. </li>
<img alt="Deployment Task" src="https://i.ibb.co/nnS7ft6/Screen-Shot-2020-08-25-at-17-03-42.png" width="600px" height="315px" />
</ol>

### High-level Overview of Tekton
1. User interact with Kubernetes to create Task or Pipelines, which are stored in Kubernetes.
2. When user wants to run, users create Task Run or PipelineRun. Picked up by controllers, and these controllers create `pods`.
<img alt="Tekton Pipelines: architecture" src="https://i.ibb.co/ySJ4s7N/Screen-Shot-2020-08-25-at-16-14-20.png" width="600px" height="320px" />

### Secrets
- Needs secret to access Git Repo or a Container Registry (Docker Registry).
- Types
	1. basic-auth
	2. ssh-auth
- Follow these steps to configure secrets: [https://github.com/tektoncd/pipeline/blob/master/docs/auth.md](https://github.com/tektoncd/pipeline/blob/master/docs/auth.md)
- Above URL Summary: Tekton Task collect Secrets from secrets field of a ServiceAccount and uses them for checkout git repository or pull/push from/to Docker registry.
- Add your public key in your Git Repo.

<!--stackedit_data:
eyJoaXN0b3J5IjpbMjEzMTE3OTE2NSwxMjU3MzcyNTM2LC0xMj
IzNTIyMzksMTczMzI3NjgyMSwtMTg1NDM4MDU3MCw5OTUxMjcw
NjksLTYwMzE2MTQ3MSwtMTI1NzAwMTg3OSwtMTAzNzI3OTc2OC
wtMTYyNjI2MTM2NywxNDgyOTk5MDI1LC04NjYwOTM2MTksLTEy
NzI2OTUwNjEsMTMxNTI5NjcxOCwzMDU1NzU2NCwtNzczMDkyOT
E3XX0=
-->