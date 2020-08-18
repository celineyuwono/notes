## Kubernetes

### Introduction
- Kubernetes provides automation and management of containerized application (ex. app in docker) and help in deployment and scaling with ease.
- Has master and slave architecture. Master controls nodes.
- Kubeadm creates Kubernetes cluster. The main commands of kubeadm are `kube init` and `kube join`.

![A quick recap](https://i.ibb.co/LvYmSdC/Screen-Shot-2020-08-18-at-9-31-55.png)

###  Master Components

1. **Kube-apiserver:** Management part of cluster.
2. **Etcd:**
	- Stores configuration and current state of Kubernetes cluster (database).
	- Distributed key-value store.
	- Database of the cloud.
	- Anything that happens on the cloud first happens in etcd. API server writes server to etcd first, and what is in etcd and cloud will be checked if matching.
3. **Kube-scheduler:** Assigns nodes to newly created pods.
4. **Kube-controller-manager:** Regulate the state of cluster with its controllers.
	- **Node Controller:** Keeps track of the state of nodes and takes action if nodes go down.
	- **Replication Controller**: Maintain and control pods based on replication.
	- **End point Controller:** Populate end point objects (joins services and pods).
	- **Service Account and Token Controller:** Responsible for API access tokens and for default accounts of new name spaces.

### Node Components
1. **Kubelet:** Agent that runs on each node. Ensures containers are running in a pod.
2. **Kubeproxy:** Runs on each node and responsible for networking.
3. **Container Runtime:** Software to run the container (ex. Docker).

### What is a ...?

1. **Namespace:** Kubernetes supports multiple virtual clusters backed by the same physical cluster. These virtual clusters are called namespaces. (kubectl get namespace).
2. **Pod:** Basic building block of Kubernetes, smallest and simplest unit in the Kubernetes object model. A pod encapsulates an application container or multiple containers (but usually 1).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQ2OTAwNzY0OV19
-->