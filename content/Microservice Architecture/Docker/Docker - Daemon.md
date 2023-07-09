---
tags: [dockercybersec]
---
# Docker Daemon
#dockercybersec

Docker daemon or dockerd is the persistent process that manages containers. [Docker](Microservice%20Architecture/Docker/Docker.md) uses different binaries for the daemon and client. To run the daemon you type dockerd.
The Docker daemon (`dockerd`) listens for Docker API requests and manages Docker objects such as images, containers, networks, and volumes. A daemon can also communicate with other daemons to manage Docker services.

It is basically the main service responsible for managing all of the containers, images, volumes, networks, contexts, etc.



https://docs.docker.com/engine/reference/commandline/dockerd/