## Microservices, Docker, and Kubernetes

### Source URL: [https://www.youtube.com/watch?v=1xo-0gCVhTU](https://www.youtube.com/watch?v=1xo-0gCVhTU)

### Microservices

![Microservices Architecture](https://i.ibb.co/qR6nTrT/t1.png)

- Split up monolith to multiple services, like auth.
- Still has 1 user interface.
- Advantages:
	- Language independent because communicate via Http (ex. 1 microservice in Java, 1 in Go).
	- Can split each microservice into teams in workplace.
	- If 1 microservice fails, other microservice still runs.
	- Works well with containers, and that makes it scalable (biggest advantage).

### Docker
- Definition: Container system, put everything application needs into small image that can be run in any computer that has Docker. Eliminates program not running in production.

![VM vs Containers](https://i.ibb.co/ctHYSCG/Screen-Shot-2020-08-18-at-9-31-43.png)

- With Docker, containers can share bins/libs, so if they use the same bins/libs, just take up 1 space.
- Docker image size is small.
- How to create image:
	- Define Docker File: Describe build process for an image (ex. Application based on node, run npm install, npm start).
	- Put application in image.

### Container Orchestration (Amazon ECS, Kubernetes, Docker Swarm)
- Kubernetes: Automate deployment, scaling, and management of containers.
- Vocabulary:
	- **Node:** Instance of computer that is running Kubernetes. Kubelet is application that is running that communicates with the master node. Node run pods. A pod contains 1 or more containers.
	- **Service:** Handles requests coming inside Kubernetes cluster from 1 node to another or from outside wanting to hit specific microservices. Usually a load balancer, how requests should be handled within cluster.
	- **Deployment:** Define desired state. “I want three copies of this container!” Kubernetes will do it. Deployment file uses yaml or json, contains declared desire state.

![A quick recap](https://i.ibb.co/LvYmSdC/Screen-Shot-2020-08-18-at-9-31-55.png)
<!--stackedit_data:
eyJoaXN0b3J5IjpbMzE1NjY2NzU0XX0=
-->