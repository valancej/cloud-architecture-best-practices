# Azure and AWS Architecture/Core Design Principles

Outline of common best practices for architecting highly available, scalable, distibuted systems across cloud platforms. 

## Scalablity

In order to support increased amounts of users, traffic, and data size without compromising performance, systems must be designed to scale appropriately. There are two main ways to achieve scalablity of systems and resources within cloud proviers:  

### Vertical Scaling: 

Scaling vertically involves increasing specifications on specific resources. As an example, spinning down a VM in either Azure or AWS EC2, increasing memory/system/storage specs, and then starting up the VM again would accomplish this. There is however, an eventual cap on resources when doing this singularly. Moreover, this can often require significant resource downtime, thus leading to less than optimal system availability.

### Horizonal Scaling: 

