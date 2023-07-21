# k8-Notes
Why kubernetes? 
- Docker is ephemeral in nature (short life span)
- docker is simple and minimiliastic software.
- Problem in Docker:
  - single host
  - no auto healing
  - no auto scaling
  - no enterprise level support ( no - loadbalancing, firewall, autoscaling, api gateway)
- so we use k8.
- k8 is container orchestration tool
- k8 is cluster in nature (group of nodes)
- k8 has loadbalancing, firewall, autoscaling, api gateway and engterpise level support.
- container default runtime --> docker shim

K8 Architecture:
  - Master node
    - api server - is a heart of the k8, it is the communication medium to controll all the k8 services
    - etcd - is key value store database, contain all the info. of the k8 which you create.
    - scheduler - is respoinsible to create a pod on the worker node
    - controller manager - is like auto scaling - replica set contain how many replicas we need for our project
    - ccm(Cloud Controller Manager) - a Kubernetes control plane component that embeds cloud-specific control logic
  - Worket node
    - kublet - resposible for monitroing the pod' whether running or not, if not it will create a one.
    - kube-proxy - responsible for loadbalancing, networking
    - container runtime - giving the container environment for running the containers.

POD:
- definiton of how to run container
- POD single instance of process running on a cluster
- It is important to note that Pods in Kubernetes are considered ephemeral; they can be created, destroyed, and rescheduled as needed due to scaling, updates, or node failures. To ensure the availability and reliability of applications, it's common to manage Pods using higher-level abstractions like Deployments, ReplicaSets, or StatefulSets.

How to see all the resources in the kubectl ?
- kubectl get all
- kubectl get all -A (to see all the resources in entire system
