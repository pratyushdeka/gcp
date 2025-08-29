Compute Engine is Google Cloud IaaS solution. With Compute Engine
- Users can create and run virtual machines on Google infrastructure
- No upfront investments
- Thousands of virtual CPUs can run on a system that’s designed to be fast and to offer consistent performance
- Each virtual machine (VM) contains the power and functionality of a full-fledged operating system
- A VM can be configured much like a physical server by specifying 
	- the amount of CPU power and memory needed
	- the amount and type of storage needed, and 
	- the operating system

Virtual Machine
- A VM instance can be created via the Google Cloud console, the Google Cloud CLI, or the Compute Engine API
- A VM instance can run Linux and Windows Server images provided by Google or any customized versions of these images
- A VM instance can also build and run images of other operating systems and flexibly reconfigure virtual machines.

Compute Engine’s pricing and billing structure
- For the use of virtual machines
	- Compute Engine bills by the second with a one-minute minimum, and sustained-use discounts start to apply automatically to virtual machines the longer they run
		- For each VM that runs for more than 25% of a month, Compute Engine automatically applies a discount for every additional minute
	- Compute Engine also offers committed-use discounts
		- for stable and predictable workloads, a specific amount of vCPUs and memory can be purchased for up to a 57% discount off of normal prices in return for committing to a usage term of one year or three years
- Compute Engine also provide Preemptible and Spot VMs
	- Suppose you have a workload that doesn't require a human to sit and wait for it to finish - such as a batch job analyzing a large dataset
	- can save money, in some cases up to 90%, by choosing Preemptible or Spot VMs to run the job
	- A Preemptible or Spot VM is different from an ordinary Compute Engine VM in only one respect: Compute Engine has permission to terminate a job if its resources are needed elsewhere
	- Difference between Preemptible and Spot VMs
		- Spot VMs differ from Preemptible VMs by offering more features
		- Preemptible VMs can only run for up to 24 hours at a time, but Spot VMs do not have a maximum runtime
		- Pricing is same for both
- In terms of storage, Compute Engine doesn’t require a particular option or machine type to get high throughput between processing and persistent disks

Choose machine properties by:
- Using a set of predefined machine types
- Creating your own custom machine types