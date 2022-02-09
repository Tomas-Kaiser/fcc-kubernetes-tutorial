# Kubernetes Tutorial

Kubernetes (K8S) is a standard for deployment of the containerized applications into production. K8S is an open-source => it is free to use.

## What Is Kubernetes

K8S is a container orchestration system. K8S lets you create the containers on different servers, either physical or virtual. All of that is done automatically without your intevention. We just need to say to K8S how many containers we want to create based on specific image.

K8S takes care of:

- Automatic deployment of the containerized applications across different servers
- Distribution of the load across multiple servers
- Auto-scaling of the deployed applications
- Monitoring and health check of the containers
- Replacement of the failed containers

K8S supports following container runtimes:

- Docker
- CRI-O
- containerd

## POD

Pod is the smallest unit in the K8S world. Containers (one or many) are created inside of the pod.

![Pod Anatomy](./imgs/podAnatomy.png)

- We can have multiple containers running inside one pod but the most common scenario is to have `a single container per pod`.
- namespace is meant to be a pod.
- Each pod must be located on the same server (onde pod, one server)

## K8S Cluster

K8S cluster consists of nodes. Node is actually server either bare metals or virtual server. You can include multiple server to the K8S cluster. Most of the time the nodes which belongs to the same cluster are located close to each other in order to perform jobs more efficiently. Inside of the node there are pods. Pod is the smallest unit in the K8S. Each pod contain usually one container.

![Cluster Schema](./imgs/clusterSchema.png)

Our job is to create the nodes and cluster based on those nodes. Everything is automated after initial configuration and K8S will automatically deploy pods on different nodes.

How nodes comunicate to each other and how they manage?

There is a Master node in K8S cluster and other nodes in the cluster are worker nodes. Master node manages the worker nodes.It is a master node job to destribute eg. load across other worker nodes. Application is deplued to worker nodes only. Master node runs only system pods which are responsible for actuall work on the K8S cluster in general

![Cluster Schema](./imgs/masterNodeCluster.png)
