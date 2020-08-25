## Tekton Pipeline and Trigger

### Tekton Pipeline

Installing Tekton Pipelines to your cluster introduces five new Custom Resources: Tasks, Pipelines, TaskRuns, PipelineRuns and PipelineResources. Tasks contain steps (which are essentially shell commands) and can be executed by TaskRuns. Pipelines consist of multiple Tasks and are executed by PipelineRuns. To share resources between different Tasks, PipelineResources can be used. Tekton just provides a framework for executing actions in a defined, acyclic way. Its power comes from the ability to execute whatever command in whatever container on a per-step basis. Steps inside one Task share a Pod for easy communication. With keywords like “runAfter”, you control precisely the order of the Tasks to run in.

Currently, Tekton has four different kinds of PipelineResources: Git, Image, Storage and Cluster. These can be used to reference a code repository, a container image to either be built or loaded, to access stored files and to manage another Kubernetes cluster. The latter allows Tekton Pipelines to not only manipulate the Kubernetes cluster it was deployed to, but any cluster it gets handed as a resource.

### Cloud Native
- Opensource.
- Microservice in containers.
- **Containers** that are dynamically orchestrated.
- Easily scale-in/out
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExOTUzODkyNDUsLTE1NzU0NjU4NzUsLT
Q1MzE5OTAwNl19
-->