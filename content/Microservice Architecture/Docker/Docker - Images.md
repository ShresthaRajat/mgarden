---
tags: [containers, docker, images]
title: Docker images
aliases: [Docker images]
linter-yaml-title-alias: Docker images
date created: Monday, July 10th 2023, 12:40:08 am
date modified: Monday, July 10th 2023, 12:40:42 am
---
# Docker images
#containers #docker #images

A docker image is simply a package with all the dependencies and information needed to create a [container](container) in [Docker](Microservice%20Architecture/Docker/Docker.md). An image includes all the dependencies (such as frameworks) plus deployment and execution configuration to be used by a container runtime. Usually, an image derives from multiple base images that are layers stacked on top of each other to form the container's filesystem. An image is immutable once it has been created.


## Dockerfile
Docker images are built with a simple text file containing instructions for how to build the Docker container image. It contains a list of command-line interface (CLI) instructions that Docker Engine will run in order to assemble the image.