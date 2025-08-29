How Google Compute Engine works with a focus on virtual networking

Many users start with GCP by defining their own virtual private cloud inside their first GC project or by starting with the default virtual private cloud.

Project -> Virtual Private Cloud -> Custom VPC or Default VPC

What is virtual private cloud (VPC)?
A VPC is a secure, individual, private cloud-computing model hosted within a public cloud. On a VPC, customers can
- Run code, store data, host websites, and anything else that can be done in an ordinary private cloud
- A virtual private cloud is hosted remotely by public cloud provider
This means that VPCs combine the scalability and convenience of public cloud computing with the data isolation of private cloud computing

Public cloud -> VPC <- Private cloud

VPC
- VPC networks connect Google Cloud resources to each other and to the internet. This includes
	- Segmenting networks
	- Using firewall rules to restrict access to instances, and 
	- Creating static routes to forward traffic to specific destinations
- Google Cloud VPC networks are global and can have subnets in any Google cloud region worldwide
	- Subnets are segmented piece of the larger network
	- Subnets can span the zones that make up a region. This architecture makes it easy to define network layouts with globals scope
	- Resources can even be in different zones on the same subnet
	- The size of a subnet can be increased by expanding the range of IP addresses allocated to it, and doing so won't affect virtual machines that are already configured
	- For example, let's take a VPC network that has three subnets defined in the us-west1 and us-east1 regions. If the VPC has two compute engine VMs attached to it, it means they are neighbours on the same subnet even though they're in different zones
This capability can be used to build solutions that are resilient to disruptions yet retain a simple network layout

The following example illustrates a custom mode VPC network with three subnets in two regions:

![[vpc-overview-example.svg]]

- _Subnet1_ is defined as `10.240.0.0/24` in the us-west1 region.
    - Two VM instances in the us-west1-a zone are in this subnet. Their IP addresses both come from the available range of addresses in _subnet1_.
- _Subnet2_ is defined as `192.168.1.0/24` in the us-east1 region.
    - Two VM instances in the us-east1-b zone are in this subnet. Their IP addresses both come from the available range of addresses in _subnet2_.
- _Subnet3_ is defined as `10.2.0.0/16`, also in the us-east1 region.
    - One VM instance in the us-east1-b zone and a second instance in the us-east1-c zone are in _subnet3_, each receiving an IP address from its available range. Because subnets are regional resources, instances can have their network interfaces associated with any subnet in the same region that contains their zones.