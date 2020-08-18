## Kubernetes Service

### Source URL: [https://www.youtube.com/watch?v=aSrqRSk43lY](https://www.youtube.com/watch?v=aSrqRSk43lY)

<![if !vml]>![A person holding a sign

Description automatically generated](file:////Users/ts-celine.yuwono/Library/Group%20Containers/UBF8T346G9.Office/TemporaryItems/msohtmlclip/clip_image001.png)<![endif]>

Service

<![if !supportLists]>· <![endif]>Each pod has a different IP address, but when pod dies, the IP address changes.

<![if !supportLists]>· <![endif]>So, if we want to access pod from different pod, we must have a more stable IP.

<![if !supportLists]>· <![endif]>Service registry and discovery is built in to solve the issue.

<![if !supportLists]>· <![endif]>In your yaml, specify service (kind: service) for each pod. The result is that the cluster IP for the replica of each pod in different nodes will be the same (see picture).

<![if !supportLists]>· <![endif]>We can specify load balancer type for each pod (example front-end UI pod) and allow user to access that pod from that IP address.

<![if !supportLists]>· <![endif]>Services also tell other pods what your specific pod provides.

<![if !supportLists]>· <![endif]>While pods come and go, the service IP addresses and ports remain the same. And other applications can find your service through Kurbenetes service discovery.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3ODc4NDI3NThdfQ==
-->