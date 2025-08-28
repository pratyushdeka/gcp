What if you want to give permissions to a Compute Engine virtual machine, rather than to a person?

Service accounts allow you to assign specific permissions to a virtual machine, so it can interact with other cloud services without human intervention.

Let’s say you have an application running in a virtual machine that needs to store data in Cloud Storage, but you don’t want anyone on the internet to have access to that data - just that particular virtual machine. You can create a service account to authenticate that VM to Cloud Storage.

Service account
- Named with an email address
- Use cryptographic keys to access resources

So, if a service account has been granted Compute Engine’s Instance Admin role, this would allow an application running in a VM with that service account to create, modify, and delete other VMs.

In addition to being an identity, a service account is also a resource, so it can have IAM policies of its own attached to it.