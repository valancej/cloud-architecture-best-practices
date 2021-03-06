# Azure and AWS Architecture/Core Design Principles

Outline of common best practices for architecting highly available, scalable, distibuted systems across cloud platforms. 

## Scalablity

In order to support increased amounts of users, traffic, and data size without compromising performance, systems must be designed to scale appropriately. There are two main ways to achieve scalablity of systems and resources within cloud providers:  

### Vertical Scaling: 

Scaling vertically involves increasing specifications on specific resources. As an example, spinning down a VM in either Azure or AWS EC2, increasing memory/system/storage specs, and then starting up the VM again would accomplish this. There is however, an eventual cap on resources when doing this singularly. Moreover, this can often require significant resource downtime, thus leading to less than optimal system availability.

### Horizonal Scaling: 

Scaling horizontally involves increasing the number of resources (ex. adding additional VMs to support an application's needs). Depending on what the architecture of an application allows, this can be a great option for distribution of workloads across multiple servers to meet demand. Amazon's Elastic Load Balancer is an example of a service that provides load balancing and support across multiple VMs for increased elasticity.


## Infrastructure as Code

Infrastructure as Code is the process of managing and provisioning infrastructure (VMs, networks, load balancers) with a declaritive approach while setting configurations for these resources using definition files (Azure Resource Manager Templates or AWS CloudFormation templates). 

Benefits: 

* Flexibility and acceleration of deployment.
* Reusability: Templates can be altered to repeat a similar deployment.
* Idempotence: Always the same configuration, regardless of the environment's starting state. 

DevOps teams who implement IaC will be able to deliver stable environments rapily and at scale. Unified best practices can easily be implemented as these teams expand. 

## Automation

Automation within cloud providers allows you to automate tasks that may be error prone, costly, or unstable. This can free up engineering teams to focus on constant improvements of these processes without getting bogged down with mundane tasks. Automation grealy improves the efficiency of engineering teams, while allowing these teams to lower their operational costs. 

There are several tools which allow for automation:

* Auto Scaling in both Azure and AWS allow users to maintain application availablity along with the ability to scale VM capacity up or down automatically. Users can also use availablity zones to ensure they are running the appropriate number of virtual machine instances across these zones to meet demand. Leveraging auto scaling groups spread across AZs allows for increased application availability should an AZ or VM become unstable or unhealthy. 

* AWS Elastic Beanstalk allows users to deploy applications and let AWS take care of provisioning the appropriate resources, scaling the application when necessary, and configuring the application for health monitoring. 

* AWS CloudWatch allows users to monitor for specific events across their provisioned resources/services and be notified if a metric goes beyond a threshold. These monitors can also trigger other events in the case of a failure. 