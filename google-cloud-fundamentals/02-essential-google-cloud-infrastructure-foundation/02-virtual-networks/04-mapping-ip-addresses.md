External IPs are mapped to internal IPs transparently by VPC.

DNS resolution for internal addresses
- Google Cloud has two types of internal DNS
	- Zonal
	- Global
- Each instance has a hostname that can be resolved to an internal IP address
	- The hostname is same as the the instance name
	- FQDN is [hostname].[zone].c.[project-id].internal
	- Example: my-server.us-central1-a.c.guestbook-151617.intenal
- If an instance is deleted or recreated, the internal IP address can change
- Name resolution is handled by internal DNS server
	- Provided as part of compute engine (169.254.169.254)
	- Configured for use on instance via DHCP
	- Provides answer for internal and external addresses

DNS resolution for external addresses
- Instances with external IP addresses can allow connections from hosts outside of the project
	- Users connect directly using external IP address
	- Admins can also publish public DNS records pointing to the instance
		- Public DNS record are not published automatically
- DNS records for external addresses can be published using existing DNS servers (outside Google Cloud)
- DNS zones can be hosted using Cloud DNS

Host DNS zones using __Cloud DNS__
- Google's DNS service
- Cloud DNS is a scalable, reliable, and managed authoritative Domain Name System, or DNS, service running on the same infrastructure as Google
- Translate domain names into IP address
	- Cloud DNS translates requests for domain names like google.com into IP addresses
- Provides low latency
- Provides high availability (100% uptime SLA for domains configured in Google DNS) 
- Create and update millions of DNS records
- Can use UI, CLI or API

Alias IP ranges
- Assign a range of internal IP addresses as aliases to a VM's network interface using alias IP ranges
- Useful if multiple services running on a VM, wants to assign a different IP address to each service
- Can configure multiple IP addresses, representing containers or applications hosted in a VM, without having to define a separate network interface
- Example Subnet:
	- Primary CIDR range 10.1.0.0./16
	- Secondary CIDR range 10.2.0.0/20