A project: 
- Key organiser of infrastructure resources in GCP
	- Associates objects and services with billing
	- Contains networks (up to 15) that can be shared/peered

A network:
- Networks can be shared with other projects, or they can be peered with other networks in other projects
- Has no IP address range but are simply a construct of all of the individual IP addresses and services within that network
- Is global and spans all available regions
	- One network can exist anywhere in the world - Asia, Europe, Americas - all simultaneously
- Contains subnetworks
	- segregate your resources with regional subnetworks
- Is available as default, auto and custom

3 VPC network Types
- Default
	- Every project is provided with a default VPC network with preset subnets and firewall rules
	- One subnet per region
		- a subnet is allocated for each region with non-overlapping CIDR blocks and firewall rules that allow ingress traffic for ICMP, RDP, and SSH traffic from anywhere, as well as ingress traffic from within the default network for all protocols and ports
	- Default firewall rules
- Auto Mode
	- Default network
	- One subnet per region
	- Regional IP allocation
	- Fixed /20 subnetwork per region
	- Expandable up to /16
	- Subnets fit within the 10.128.0.0/9 CIDR block
- Custom Mode
	- No default subnets created
	- Full control of subnets and the IP ranges
		- These IP ranges cannot overlap between subnets of the same network
	- Regional IP allocation
	- Expandable to IP ranges you specify

	Conversion of Auto mode network to custom mode network is possible to take advantage of the control that custom mode networks provide but this conversion is __one way__ 

Suppose a project have 5 networks across all the regions. Network#1 have two VMs each in us-east1 (A) and europe-west1 (B). Network#3 have one VM in us-east1 (C) region and Network#4 have one VM in us-east1 (D) region. 
- A and B VMs can communicate over internal IPs even though they are in different regions but in same network
- C and D must communicate over external IPs even though they are in the same region but different network

Google's VPC is global
- VM instances within a VPC network can communicate privately on a global scale, a single VPN can securely connect your on-premises network to your Google Cloud network
- Even though two VM instances are in separate regions (us-west1 and us-east1), they leverage Google’s private network to communicate between each other and to an on-premises network through a VPN gateway
- This reduces cost and network management complexity

Subnetworks cross zones
- Subnetworks on a regional scale so subnetworks can cross zones
- **Every subnet has four reserved IP address in its primary IP range**
	- First two IP addresses .0 and .1 are reserved for the network and the subnet gateway respectively
	- Second-to-last and the last IP addresses in the range are reserved. The last address is reserved as the broadcast address
- VMs can be on the same subnet but in different zones
- A single firewall rule can be applied to the VMs

Expand subnets without re-creating instances
- Google Cloud VPCs let you increase the IP address space of any subnets without any workload shutdown or downtime but the below things to remember
	- The new subnet cannot overlap with other subnets in the same VPC network in any region
	- IP range must be a unique valid CRDR block
	- New subnet IP ranges have to fall within valid IP ranges
	- **Can expand but not shrink**
	- Auto mode can be expanded from /20 to /16, but no larger
	- Can convert the auto mode subnetwork to a custom mode subnetwork to increase the IP range further
	- Avoid large subnets
		- Overly large subnets are more likely to cause CIDR range collisions when using Multiple Network Interfaces and VPC Network Peering, or when configuring a VPN or other connections to an on-premises network