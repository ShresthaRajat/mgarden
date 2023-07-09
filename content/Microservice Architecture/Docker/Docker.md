---
tags: [containers, virtual-machines, docker]
---
# Docker
#containers #virtual-machines #docker


Docker is an open source platform for building, deploying, and managing containerized applications. Docker is simply a popular implementation of [Containers](Microservice%20Architecture/Docker/Containers.md) and has become a standard in the industry.

Docker uses a client-server architecture. The Docker _client_ talks to the [Docker - Daemon](Microservice%20Architecture/Docker/Docker%20-%20Daemon.md), which does the heavy lifting of building, running, and distributing your Docker containers. The Docker client and daemon _can_ run on the same system, or you can connect a Docker client to a remote Docker daemon. The Docker client and daemon communicate using a REST API, over UNIX sockets or a network interface. Another Docker client is Docker Compose, that lets you work with applications consisting of a set of containers.
![Pasted image 20221017160401](Attachments/Pasted%20image%2020221017160401.png)