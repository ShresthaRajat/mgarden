# AKS
#Azure #cloud #Kubernetes #microservices #managed-kubernetes-cluster

AKS is a fully managed [Kubernetes](Microservice%20Architecture/Kubernetes/Kubernetes.md) container management service by Microsoft [Azure](Cloud%20Computing/Azure/Azure.md). Along with [Azure DevOps](DevOps/CICD/Azure%20DevOps.md) It offers a robust Serverless Continios Integration and Contious Deployment experience. 

In AKS the users will just need to pay for the nodes that are being used. Which means the other services such as the Azure managed Control pane is free AKSAKSof cost.

## Control plane
When you create an AKS cluster, a control plane is automatically created and configured. This control plane is provided at no cost as a managed Azure resource abstracted from the user. You only pay for the nodes attached to the AKS cluster. The control plane and its resources reside only on the region where you created the cluster.

![Pasted image 20220928225117](Microservice%20Architecture/Attachments/Pasted%20image%2020220928225117.png)


## Node pools
Node pools use virtual machine scale sets as the underlying infrastructure to allow the cluster to scale the number of nodes in a node pool. New nodes created in the node pool will always be the same size as you specified when you created the node pool.
![Pasted image 20220930162008](Microservice%20Architecture/Attachments/Pasted%20image%2020220930162008.png)


## Networking
An Azure Kubernetes Service (AKS) cluster blocks all inbound traffic from the internet to the cluster to assure network security. Deployed workloads in Kubernetes are, by default, only accessible from inside the cluster. To expose the applications to the outside world, you need to open specific ports and forward them to your services. The network configuration for containers is temporary. A container's configuration and the data in it isn't persistent between executions. After you delete a container, all information is gone unless it's configured to use a volume. The same applies to the container's network configuration and any IP addresses assigned to it.

Kubernetes has two network availability abstractions that allow you to expose any app: _services_ and _ingresses_ They're both responsible for allowing and redirecting the traffic from external sources to the cluster.

## Service
A Kubernetes service is a workload that abstracts the IP address for networked workloads. A Kubernetes service acts as a load balancer and redirects traffic to the specified ports by using port-forwarding rules.

A diagram that shows two Kubernetes services. The first service is applied to one pod. The second service is applied to two pods.

You define a service in the same way as a deployment, by using a YAML manifest file. The service uses the same selector key as deployments to select and group resources with matching labels into one single IP.

A Kubernetes service needs four pieces of information to route traffic.

| Information|Description     |
| --- | --- |
|  **Target resource** |The target resource is defined by the `selector` key in the service manifest file. This value selects all the resources with a given label onto a single IP address.       |
|**Service port** |This port is the inbound port for your application. All the requests come to |this port from where the service forwards the requests to the resource.
|**Network protocol** |This value identifies the network protocol for which the service will forward network data.|
|**Resource port** | This value identifies the port on the target resource on which incoming requests are received. This port is defined by the `targetPort` key in the service manifest file. |
### Types of services:

Services can be of several types. Each type changes the behavior of the applications selected by the service.

-   **ClusterIP**: This value exposes the applications internally only. This option allows the service to act as a port-forwarder and makes the service available within the cluster. This value is the default when omitted.
    
-   **NodePort**: This value exposes the service externally. It assigns each node a static port that responds to that service. When accessed through `nodeIp:port`, the node automatically redirects the request to an internal service of the `ClusterIP` type. This service then forwards the request to the applications.
    
-   **LoadBalancer**: This value exposes the service externally by using Azure's load-balancing solution. When created, this resource spins up an Azure Load Balancer resource within your Azure subscription. Also, this type automatically creates a `NodePort` service to which the load balancer's traffic is redirected and a `ClusterIP` service to forward it internally.
    
-   **ExternalName**: This value maps the service by using a DNS resolution through a CNAME record. You use this service type to direct traffic to services that exist outside the Kubernetes cluster.

## Ingress Controller
Ingress controllers provide the capability to deploy and expose your applications to the world without the need to configure network-related services. 

Ingress controllers create a reverse-proxy server that automatically allows for all the requests to be served from a single DNS output. You don't have to create a DNS record every time a new service is deployed. The ingress controller will take care of it. When a new ingress is deployed to the cluster, the ingress controller creates a new record on an Azure managed DNS zone and links it to an existing load balancer. This functionality allows for easy access to the resource through the internet without the need for additional configuration.

- Acts as a reverse proxy to allow external URLs.
- Might act as a load balancer.
- Terminates SSL/TLS requests.
- Offers name-based virtual hosting.

![Pasted image 20220930162708](Microservice%20Architecture/Attachments/Pasted%20image%2020220930162708.png)

![Pasted image 20220930162112](Microservice%20Architecture/Attachments/Pasted%20image%2020220930162112.png)


## Demo
To setup a basic AKS cluster which simply hosts a static webapp.

### Requirements
1. An Azure subscription with basic authority to create AKS cluster and related services (i.e. Compute instances, Container Registry).


### Steps:
1. Create a resource group to organize the azure services that are going to be used in the project.
2. Create the cluster
		- Select the resource-group for the AKS Cluster
		- Fill in the basic stuffs (Cluster name, Region, Kubernetes version)
		- Create only 1 node
		- Configure other settings (node-pools, authentication, networking, Integration and tags)
		- Create the cluster
3.  copy the [azure-vote deployment yml](https://github.com/Azure-Samples/azure-voting-app-redis/blob/master/azure-vote-all-in-one-redis.yaml) and apply it
TODO: modify yml to run simple nginx webserver to host a page

```bash
# create a container registry and resource group
az group create --name test-nginx --location uksouth
az acr create --resource-group test-nginx \
--name testNginx --sku Basic

# upload docker image to acr
cd ~/Documents/nginx-example
az acr build --image testnginx \
--registry testNginx \
--file dockerfile .

#  create a aks cluster
az group create --name test-nginx --location uksouth
az aks create --resource-group test-nginx --name nginx-cluster --node-count 2 --enable-addons monitoring --generate-ssh-keys

# after setting up the cluster set the local cli scubcription for the kubectl
az account set --subscription xxxxxxxxxxxxx
az aks get-credentials --resource-group test-nginx --name nginx-cluster
# after running the previous command your local machine 
# will have access to the kubernetes api and you can finally run kubectl command

# download the azure-vote yml
curl https://raw.githubusercontent.com/Azure-Samples/azure-voting-app-redis/master/azure-vote-all-in-one-redis.yaml > azure-vote.yml

# apply the azure-vote.yml deployment
kubectl apply -f azure-vote.yml

# fetch the ip of the loadbalancer 
get svc azure-vote-front --watch

```

## References
https://learn.microsoft.com/en-us/azure/aks/concepts-clusters-workloads
https://github.com/Azure-Samples/azure-voting-app-redis/blob/master/azure-vote-all-in-one-redis.yaml
https://github.com/Azure-Samples/azure-voting-app-redis
https://collabnix.github.io/kubelabs/pods101/deploy-your-first-nginx-pod.html
https://learn.microsoft.com/en-us/training/modules/aks-deploy-container-app
