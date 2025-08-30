Kubernetes
- Open-source platform for managing containerised workloads and services
- Makes it easy to orchestrate many containers on many hosts, scale them as microservices, and deploy rollouts and rollbacks
- Is a set of APIs to deploy containers on a set of nodes called a cluster
- Divided into a set of primary components that run as the control plane and a set of nodes that run containers
- You can describe a set of applications and how they should interact with each other and kubernetes figures how to make that happen

Pod
- The smallest unit in Kubernetes that you can create or deploy
- It represents a running process on your cluster as either a 
	- component of an application or
	- an entire app
- Generally, you only have one container per Pod, but if you have multiple containers with a hard dependency, you can package them into a single pod and share networking and storage resources between them
- Provides a unique network IP and set of ports for your containers and configurable options that govern how your container should run
- Run a container in a Pod in Kubernetes, use _kubectl run_ command, which starts deployment with a container running inside a Pod

Deployment
- represents a group of replicas of the same Pod and keeps your Pods running even when the nodes they run on fail
- could represent
	- component of an application or
	- an entire app
- To see a list of running Pods, use _kubectl get pods_ command