## Helm

### Source URL: [https://www.youtube.com/watch?v=-ykwb1d0DXU&list=PLy7NrYWoggjw0OMxUDIImjWQjM7qZWn_R&index=3](https://www.youtube.com/watch?v=-ykwb1d0DXU&list=PLy7NrYWoggjw0OMxUDIImjWQjM7qZWn_R&index=3)

### What is Helm?
- **Helm** is a package manager for Kubernetes similar to  apt, yum, brew.
- We can package YAML File and distribute it to our own repositories in Helm Hub (similar to Docker Hub). There are two kind of repositories, public that anyone can use and private, which is used for companies who don’t want to publish their YAML settings.
- **Helm** **Charts** are bundle of YAML files that you push into your Helm repository. We can download and use existing Helm charts from other repositories as well. Commonly used Kubernetes deployments like mySQL has their own  Helm Chart.
- Helm has multiple uses. First of all, it acts as a **templating engine**. Most YAML files of different pods will be similar, so we can use dynamic values.  Values are defined in a file called values.yaml (default name). This values file will replace the variables to our template file.This is practical for CI/CD, for example deploying  to multiple environments.
- `Helm install <chart name>` will overlay values.yaml to template files. You can also make a different file, for example values-2.yaml file and use helm install --values=values-2.yaml <chart name> to override the original file and values.yaml.

<![if !supportLists]>· <![endif]>Helm also helps in **r****elease management**. The Version 2 of Helm consists of the Helm CLI (client) and Tiller (server). Helm CLI will send YAML files to Tiller, which runs in the Kubernetes cluster. Tiller will execute the request and create or change components inside the Kubernetes cluster.  Tiller will also save a copy of your Helm Chart for future reference, creating a history of chart executions called the **chart history**. How Helm works is that it will compare the previous chart and current chart and make changes to the deployment based on the differences of the charts.  In case of an upgrade  goes wrong, we can rollback. The downside is Tiller has too much permissions in Kubernetes Cluster; It can create, update, and delete components itself. This is a big security issue.  Helm 3 solves this by removing Tiller, but that means that the release management feature is nonexistent.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEzMTAyMDQzOTRdfQ==
-->