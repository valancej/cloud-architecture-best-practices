# Azure and AWS Architecture/Core Design Principles

Outline of common best practices for architecting highly available, scalable, distibuted systems across cloud platforms. 

## Scalablity

In order to support increased amounts of users, traffic, and data size without compromising performance, systems must be designed to scale appropriately. There are two main ways to achieve scalablity of systems and resources within cloud providers:  

### Vertical Scaling: 

Scaling vertically involves increasing specifications on specific resources. As an example, spinning down a VM in either Azure or AWS EC2, increasing memory/system/storage specs, and then starting up the VM again would accomplish this. There is however, an eventual cap on resources when doing this singularly. Moreover, this can often require significant resource downtime, thus leading to less than optimal system availability.

### Horizonal Scaling: 

Scaling horizontally involves increasing the number of resources (ex. adding additional VMs to support an application's needs). Depending on what the architecture of an application allows, this can be a great option for distribution of workloads across multiple servers to meet demand. Amazon's Elastic Load Balancer is an example of a service that provides load balancing and support across multiple VMs for increased elasticity.


## Infrastructure as Code


