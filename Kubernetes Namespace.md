## Kubernetes Namespaces

### Source URL: [https://www.youtube.com/watch?v=K3jNo4z5Jx8](https://www.youtube.com/watch?v=K3jNo4z5Jx8)

- What is a namespace? Virtual cluster inside a cluster.
- Use cases:
	1. Grouping applications by task (ex. database, nginx, frontend).

<![if !supportLists]>3. <![endif]>Resource sharing and multiple dev stages, example: Staging, Dev. In this case, replicate frontend but use the same nginx is also possible.

<![if !supportLists]>4. <![endif]>Access resource and resource limit in namespaces (See “What isolates Linux Containers to one another? 7 namespaces.” notes above).

<![if !supportLists]>· <![endif]>Characteristics of namespaces

<![if !supportLists]>1. <![endif]>Cannot access most resources from another namespace. If want to do so, must use configmap.

<![if !supportLists]>2. <![endif]>But you can access through service! Specify resources you want to share.

<![if !supportLists]>3. <![endif]>There are some components that cannot be in a namespace like volumes.
<!--stackedit_data:
eyJoaXN0b3J5IjpbNzE2NDcwMzA2XX0=
-->