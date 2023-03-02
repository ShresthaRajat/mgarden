￼ # AKS Full Demo

#Azure #Kubernetes #AKS #Nginx #Helm #Ingress #TLS #CICD
[AKS](Microservice%20Architecture/AKS/AKS.md)
AKS Full demo with following features:

- Good Namespace organization
- Nginx Ingress controller
- host based ingress routing (redirecting to at least 2 pods)
- TLS termination using ingress
- Helm to manage all of the yml files
- Automated deployments 

## Steps:

### Step 1: Create a cluster in Azure
To create a cluster in azure you will require a valid azure subscription. Additional tools such as azcli, kubectl and helm is reccomended to be installed. Follow the Instructions on the main [AKS - Full Demo](Microservice%20Architecture/AKS/AKS%20-%20Full%20Demo.md) note.


### Step 2: Configure Ingress Controller
After creating the cluster you will then need an ingress controller which will link up the Azure Loadbalancer with the AKS cluster. luckily, this is fairly simple to setup and will require only helm to setup. This will essentially install the Ingress controller which can then be used to setup Several ingress service. Follow the guide [AKS - Ingress Controller](Microservice%20Architecture/AKS/AKS%20-%20Ingress%20Controller.md) to install, configure, and run apps with a public IP


