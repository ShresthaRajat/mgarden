---
tags: [kubernetes, cloud-native, microservices, containers]
---
what does waf do# Kubernetes

#kubernetes #cloud-native #microservices #containers

An opensource Container Management or Container **Orchestration tool** which basically automates the operations related to [Containers]. Basic usage of kubernetes is to automate [container](container) deployment, auto-scaling, operating, and managing it. In most cases it works by running [Docker](Microservice%20Architecture/Docker/Docker.md) containers on top of [Docker - Daemon](Microservice%20Architecture/Docker/Docker%20-%20Daemon.md) setup on top of nodes in the cluster.

It is developed by google and is later donated to CNCF. It is fully opensource and is made using [golang](golang). Kubernetes is often abbreviated as **K8s**.

![Pasted image 20221016000801](Attachments/Pasted%20image%2020221016000801.png)


## Key words
1. Cluster: Group of Nodes which are interconnected.
2. Node: A single compute unit (virtual or bare-metal) which helps to host containers inside of them.
3. Master: Master node which controls the cluster.
4. Service: An object on Master that provides load-balancing across a replicated groups of pods or a single pod.
5. Replication Controller: It ensures the normal operation of the applications by managing the normal operations of the pods.
6. Worker Nodes: A basic compute unit which help host pods. It as a kubernetes application (Kubelet) which helps the communication between the main master node but doesn't have the main kubernetes daemon on it. The worker node will also contain docker Daemon which enables the use of containers.
7. Deployment: xxxxxxxxxxxxxxx
8. 
9. Pods: A Logical collection of containers which forms a basic application.
10. [Containers]: A simple package of application and its dependencies created to do something.
11. Container Registry: 

*Some of these services are explored in detail later on this document*

*Kubernetes requires at least a node in which the Kubernetes master is installed at which then controls any additional nodes.*

## How it works
Kubernetes works with the help of a main Kubenetes master application which runs on a computer. The main Kubernetes master is also known as a master nodes. It then manages other nodes also known as Worker nodes. The master node contains the main kubernetes master service which provides the user with essential API to do various operations to the services that takes instructions from the main administrator and operated accordingly. Another key component of the kubernetes is the Image Registry service which is usually third party. Image registry is bacially a repository for container images usually docker.

All of these services work together to form a basic kubernetes workflow with the API provided by the master node Kubernetes daemon, Image registry providing the container images with essential application files and instructions, master nodes, and worker nodes.

![Pasted image 20220928221909](Attachments/Pasted%20image%2020220928221909.png)

A general kubernetes cluster consists of the following components:
1. Master Node ((*Required*) A node with Kubernetes Master installed)
2. Worker Nodes (Other nodes which provides the compute capabilities to the applications)

![Pasted image 20220928223829](Attachments/Pasted%20image%2020220928223829.png)


Kubernetes allows us to auto scale application automatically, by creating them from a container registry, manage them, enable several modes of communication between the containers, and also give the admin the options to secure their resources. 

![Pasted image 20220928221530](Attachments/Pasted%20image%2020220928221530.png)