---
tags: [kubernetes, Helm]
---
# Helm
#kubernetes #Helm

Helm is basically a package manager for [Kubernetes](Microservice%20Architecture/Kubernetes/Kubernetes.md) which is used to automates the process of installing, upgrading, configuring, and removing software in a consistent manner. It is used to package yaml files and distribute them in public / private repositories,  manage/create kubernetes deployments with one command.

It is quite powerful due to its templeting capabilities. You can use helm to define multiple pod/service/ingress definition using a [DRY](DRY) template which helps you use a single file to configure common variables that could be interchanged throughout  the operation of the application on the cluster.

Some of the tasks that helm enables us to do are:
-   create new charts from scratch
-   package charts into chart archive (tgz) files
-   interact with chart repositories where charts are stored
-   install and uninstall charts into an existing Kubernetes cluster
-   manage the release cycle of charts that have been installed with Helm

## Helm Client
 Helm client is a command-line tool for end user which aids in:
-   local chart development
-   managing repositories
-   managing releases
-   interfacing with the Helm library
-   sending charts to be installed
-   requesting upgrading or uninstalling of existing releases

## Helm Library
Helm Library are the projects that provides the logic for executing all Helm operations and  interfaces with the Kubernetes API server. It also help  provides the following capability:
     -   combining a chart and configuration to build a release
     -   installing charts into Kubernetes, and providing the subsequent release object
     -   upgrading and uninstalling charts by interacting with Kubernetes
