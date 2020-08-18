<![endif]-->

Introduction to Microservices, Docker, and Kubernetes

[https://www.youtube.com/watch?v=1xo-0gCVhTU](https://www.youtube.com/watch?v=1xo-0gCVhTU)

screenshot

Microservices

- Split up monolith to multiple services, like auth.

<![if !supportLists]>· <![endif]>Still has 1 user interface.

<![if !supportLists]>· <![endif]>Advantages:

<![if !supportLists]>o <![endif]>Language independent because communicate via Http (ex. 1 microservice in Java, 1 in Go)

<![if !supportLists]>o <![endif]>Can split each microservice into teams in workplace.

<![if !supportLists]>o <![endif]>If 1 microservice fails, other microservice still runs.

<![if !supportLists]>o <![endif]>Works well with containers, and that makes it scalable (biggest advantage).

Docker

<![if !supportLists]>· <![endif]>Definition: Container system, put everything application needs into small image that can be run in any computer that has Docker. Eliminates program not running in production.

<![if !vml]>![A screenshot of a cell phone

Description automatically generated](file:////Users/ts-celine.yuwono/Library/Group%20Containers/UBF8T346G9.Office/TemporaryItems/msohtmlclip/clip_image002.png)<![endif]>

<![if !supportLists]>· <![endif]>With Docker, containers can share bins/libs, so if they use the same bins/libs, just take up 1 space.

<![if !supportLists]>· <![endif]>Docker image size is small.

<![if !supportLists]>· <![endif]>How to create image:

<![if !supportLists]>o <![endif]>Define Docker File: Describe build process for an image (ex. Application based on node, run npm install, npm start).

<![if !supportLists]>o <![endif]>Put application in image.

Container Orchestration (Amazon ECS, Kubernetes, Docker Swarm)

<![if !supportLists]>· <![endif]>Kubernetes: Automate deployment, scaling, and management of containers.

<![if !supportLists]>· <![endif]>Vocab:

<![if !supportLists]>o <![endif]>Node: Instance of computer that is running Kubernetes. Kubelet is application that is running that communicates with the master node. Node run pods. A pod contains 1 or more containers.

<![if !supportLists]>o <![endif]>Service handles requests coming inside Kubernetes cluster from 1 node to another or from outside wanting to hit specific microservices. Usually a load balancer, how requests should be handled within cluster.

<![if !supportLists]>o <![endif]>Deployment: Define desired state. “I want three copies of this container!” Kubernetes will do it. Deployment file uses yaml or json, contains declared desire state.

<![if !vml]>![A screenshot of a computer

Description automatically generated](file:////Users/ts-celine.yuwono/Library/Group%20Containers/UBF8T346G9.Office/TemporaryItems/msohtmlclip/clip_image003.png)<![endif]>
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTczNDUxOTkwM119
-->