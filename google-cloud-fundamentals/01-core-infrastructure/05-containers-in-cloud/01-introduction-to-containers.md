
A container:
- is an invisible box around your code and its dependencies
- has limited access to its own partition of the file system and hardware
- only requires a few system calls to create and it starts as quickly as a process
- Only needs an OS kernel that supports containers and a container runtime, on each host
- Scales like PaaS, but gives nearly the same flexibility as IaaS
