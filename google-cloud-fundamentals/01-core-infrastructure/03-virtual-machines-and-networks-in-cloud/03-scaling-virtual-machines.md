With Compute Engine, we can choose the most appropriate machine properties for our instances by:
- Using a set of predefined machine types
- Creating your own custom machine types

To do this, Compute Engine has a feature called Autoscaling, where VMs can be added to or subtracted from an application based on load metrics. The other part of making that work is balancing the incoming traffic among the VMs. Google’s Virtual Private Cloud (VPC) supports several different kinds of load balancing.

With Compute Engine, you can in fact configure very large VMs, which are great for workloads such as in-memory databases and CPU-intensive analytics, but most Google Cloud customers start off with scaling out, not up.

Maximum number of CPUs per VM
- tied to its machine family
- constrained by the user's quota, which is zone dependent

Specifications for currently available VM machine types can be found at cloud.google.com/compute/docs/machine-types