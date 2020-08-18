### Stateful Sets in Kubernetes

### Source URL: [https://www.youtube.com/watch?v=pPQKAR1pA9U&list=PLy7NrYWoggjw0OMxUDIImjWQjM7qZWn_R](https://www.youtube.com/watch?v=pPQKAR1pA9U&list=PLy7NrYWoggjw0OMxUDIImjWQjM7qZWn_R)

### Examples
- Kubernetes Component used for Stateful Applications: Database like SQL, Elasticsearch or applications that save data.
- Other examples: node.js (stateless) and mongoDB (stateful).

### Deployment
- Deployment of **stateless** vs **stateful apps** different with Kubernetes.
- **Stateless apps** are deployed using `Deployment` (and can replicate).
- **Stateful apps** are deployed using `StatefulSet` (can replicate too).
- Both have service to **load balance** between pods.

### Deployment vs StatefulSet
- **Deployments** are easy to replicate.
	- Created in random order and hashes vs fixed order names in StatefulSet.
	- Service load balances between pods.
- **StatefulSet** are harder to replicate.
	- Stateful apps cannot be created/deleted at the same time.
	- They cannot be randomly addressed because replica pods are not identical, have their own pod identity.
	- There is a master pod, that allows read and write to database, and slave pods, which only allows read.
	- Slave pods continuously synchronize with master pod.
	- When a new slave pod is added, the new slave pod will copy data from previous slave pod (fixed order names).
![Scaling database applications](https://i.ibb.co/C7VWg08/Screen-Shot-2020-08-18-at-10-39-11.png)
	- With persistent storage, data will be duplicated to host file system so if all pods die, the data won’t be lost (see docker volume images).
	- Each pod has their own **persistent volume** (each data is stored in different physical servers) containing data and pod state (master or slave). This is should not in local but remote in case of pod crash.

### Creation and Deletion
- Created with last fixed order names.
- Deleted from last fixed order names.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4NzAyNjAxMTZdfQ==
-->