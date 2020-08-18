## Kubernetes Service

### Source URL: [https://www.youtube.com/watch?v=aSrqRSk43lY](https://www.youtube.com/watch?v=aSrqRSk43lY)

![Kubernetes Explained](https://i.ibb.co/y8gMPpg/Screen-Shot-2020-08-18-at-10-44-29.png)

- Each pod has a different IP address, but when pod dies, the IP address changes.
- So, if we want to access pod from different pod, we must have a more stable IP.
- **Service Registry** and **Service Discovery** is built in to solve the issue.
- In your YAML file, specify service `kind: service` for each pod. The result is that the cluster IP for the replica of each pod in different nodes will be the same (see picture).
- We can specify **load balancer** type for each pod (ex. front-end UI pod) and allow user to access that pod from that IP address.
- Services also tell other pods what your specific pod provides.
- While pods come and go, the service IP addresses and ports remain the same. And other applications can find your service through Kurbenetes Service Discovery.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTUzMTcyMzQ0Ml19
-->