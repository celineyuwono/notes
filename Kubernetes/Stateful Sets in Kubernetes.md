### Stateful Sets in Kubernetes

### Source URL: [https://www.youtube.com/watch?v=pPQKAR1pA9U&list=PLy7NrYWoggjw0OMxUDIImjWQjM7qZWn_R](https://www.youtube.com/watch?v=pPQKAR1pA9U&list=PLy7NrYWoggjw0OMxUDIImjWQjM7qZWn_R)

- Kubernetes Component used for Stateful Applications: Database like SQL, Elasticsearch or applications that save data.Example: node.js (stateless) and mongoDB (stateful).

<![if !supportLists]>· <![endif]>Deployment of stateless vs stateful apps different with Kubernetes.

<![if !supportLists]>· <![endif]>Stateless apps are deployed using **Deployment** (and can replicate).

<![if !supportLists]>· <![endif]>Stateful apps are deployed using **StatefulSet** (can replicate too).

<![if !supportLists]>· <![endif]>Both have service to loadbalance between pods.

<![if !supportLists]>· <![endif]>Deployment vs StatefulSet

<![if !supportLists]>o <![endif]>Deployments are easy to replicate.

<![if !supportLists]>§ <![endif]>Created in random order and hashes vs fixed order names in StatefulSet.

<![if !supportLists]>§ <![endif]>Service load balances between pods.

<![if !supportLists]>o <![endif]>StatefulSet harder to replicate.

<![if !supportLists]>§ <![endif]>Stateful apps cannot be created/deleted at the same time.

<![if !supportLists]>§ <![endif]>They cannot be randomly addressed because replica pods are not identical, have their own pod identity.

<![if !supportLists]>§ <![endif]>There is a master pod, that allows read and write to database, and slave pods, which only allows read.

<![if !supportLists]>§ <![endif]>Slave pods continuously synchronize with master pod.

<![if !supportLists]>§ <![endif]>When a new slave pod is added, the new slave pod will copy data from previous slave pod (fixed order names). <![if !vml]>![A screenshot of a cell phone

Description automatically generated](file:////Users/ts-celine.yuwono/Library/Group%20Containers/UBF8T346G9.Office/TemporaryItems/msohtmlclip/clip_image001.png)<![endif]>

<![if !supportLists]>§ <![endif]>With persistent storage, data will be duplicated to host file system so if all pods die, the data won’t be lost (see docker volume images).

<![if !supportLists]>§ <![endif]>Each pod has their own **persistent volume** (each data is stored in different physical servers) containing data and pod state (master or slave). This is should not in local but remote in case of pod crash.

<![if !supportLists]>o <![endif]>Creation and deletion. Create with last fixed order names, delete from last fixed order names.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTM0MDc3NjI0NF19
-->