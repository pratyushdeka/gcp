GKE
- Google-hosted managed Kubernetes service in the cloud
- consists of multiple machines, specifically Compute Engine instances, grouped together to form a cluster
- GKE manages all the control plane components for us
- It still exposes an IP address to which we send all of our Kubernetes API requests, but GKE takes responsibility for provisioning and managing all the control plane infrastructure behind it
- Modes
	- Autopilot
		- GKE-managed infrastructure
	- Standard
		- User-managed infrastructure

Autopilot
- Optimized for production
- Strong security posture
- Promotes operational efficiency

Standard
- Same functionality as Autopilot, but responsible for
	- Cluster configuration
	- Cluster management
	- Cluster optimization

Kubernetes provides the mechanisms through which you interact with your cluster. Kubernetes commands and resources are used to 
- deploy and manage applications
- perform administration tasks
- set policies
- monitor the health of deployed workloads

Running a GKE cluster comes with the benefit of advanced cluster management features that Google Cloud provides. These includes
- Google Cloud's load-balancing for Compute Engine instances
- Node pools to designate subsets of nodes within a cluster for additional flexibility
- Automatic scaling of your cluster's node instance count
- Automatic upgrades for your cluster's node software
- Node auto-repair to maintain node health and availability
- Logging and monitoring with Google Cloud Observability for visibility into the cluster