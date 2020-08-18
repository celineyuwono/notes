<![endif]-->

Kubernetes

<![if !supportLists]>· <![endif]>Provides automation and management of containerized application (ex. App in docker) and help in deployment and scaling with ease.

<![if !supportLists]>· <![endif]>Has master and slave architecture. Master controls nodes.

<![if !supportLists]>· <![endif]>Kubeadm creates Kubernetes cluster. The main commands of kubeadm are kube init and kube join.

<![if !vml]>![A screenshot of a computer

Description automatically generated](file:////Users/ts-celine.yuwono/Library/Group%20Containers/UBF8T346G9.Office/TemporaryItems/msohtmlclip/clip_image001.png)<![endif]>

Kubernetes Components

<![if !supportLists]>1. <![endif]>Kube-apiserver: Management part of cluster.

<![if !supportLists]>2. <![endif]>Etcd:

<![if !supportLists]>a. <![endif]>Stores configuration and current state of Kubernetes cluster (database).

<![if !supportLists]>b. <![endif]>Distributed key-value store.

<![if !supportLists]>c. <![endif]>Database of the cloud.

<![if !supportLists]>d. <![endif]>Anything that happens on the cloud first happens in etcd. API server writes server to etcd first, and what is in etcd and cloud will be checked if matching.

<![if !supportLists]>3. <![endif]>Kube-scheduler: Assigns nodes to newly created pods.

<![if !supportLists]>4. <![endif]>Kube-controller-manager: Regulate the state of cluster with its controllers.

<![if !supportLists]>a. <![endif]>Node Controller: Keeps track of the state of nodes and takes action if nodes go down.

<![if !supportLists]>b. <![endif]>Replication Controller: Maintain and control pods based on replication.

<![if !supportLists]>c. <![endif]>End point Controller: Populate end point objects (joins services and pods)

<![if !supportLists]>d. <![endif]>Service Account and Token Controller: Responsible for API access tokens and for default accounts of new name spaces.

Node Components

<![if !supportLists]>1. <![endif]>Kubelet: Agent that runs on each node. Ensures containers are running in a pod.

<![if !supportLists]>2. <![endif]>Kubeproxy: Runs on each node and responsible for networking.

<![if !supportLists]>3. <![endif]>Container Runtime: Software to run the container, ex. Docker.

What Is?

<![if !supportLists]>1. <![endif]>Namespace: Kubernetes supports multiple virtual clusters backed by the same physical cluster. These virtual clusters are called namespaces. (kubectl get namespace).

<![if !supportLists]>2. <![endif]>Pod: Basic building block of Kubernetes, smallest and simplest unit in the Kubernetes object model. A pod encapsulates an application container or multiple.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTYyMjA3Njg4MV19
-->