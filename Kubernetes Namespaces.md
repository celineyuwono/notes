## Kubernetes Namespaces

### Source URL: [https://www.youtube.com/watch?v=K3jNo4z5Jx8](https://www.youtube.com/watch?v=K3jNo4z5Jx8)

- What is a **namespace**? Virtual cluster inside a cluster.

### Use Cases of Namespaces
1. Grouping applications by task (ex. database, nginx, frontend).
2. Resource sharing and multiple stages (example: Staging, Dev. In this case, replicate frontend but use the same nginx is also possible.
3. Access resource and resource limit in namespaces (See “What isolates Linux Containers to one another? 7 namespaces.” notes above).

### Characteristics of Namespaces
1. Cannot access most resources from another namespace. If want to do so, must use configmap.
2. But you can access through service! Specify resources you want to share.
3. There are some components that cannot be in a namespace like volumes.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3MTY3NDQxMDZdfQ==
-->