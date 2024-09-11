## Six benefits of using the cloud 

- `Trade capital expense for variable expense`

  Instead of making large upfront investments in hardware and infrastructure (capital expenses), you pay only for the resources you actually use (variable expenses). This reduces financial risk and allows you to allocate funds more flexibly.

- `Benefits from massive economies of scale`
  
  Cloud providers operate at a large scale, which allows them to reduce costs and pass on the savings to customers. You gain access to the same infrastructure and services used by large companies, often at a fraction of the cost.

- `Stop guessing capacity`
  
  With the cloud, you don’t need to estimate your capacity requirements ahead of time. You can scale resources up or down based on demand, ensuring you have the right capacity without overprovisioning or underprovisioning.

- `Increased speed and agility`
  
  The cloud enables faster deployment of resources and applications, reducing the time needed to bring new products or services to market. It also provides tools and platforms that accelerate development and innovation.

- `Stop spending money running and maintaining data centers`
  
  You no longer need to invest in and manage physical data centers, including costs associated with power, cooling, and maintenance. The cloud provider handles all of these, allowing you to focus on your core business activities.

- `Go global in minutes`
  
  Cloud services are available in multiple regions worldwide. You can quickly deploy your applications and services across these regions, providing a global reach and ensuring low latency and high availability for your users, no matter where they are located.
  
## Virtualization

`Virtualization` is a technology that allows you to create multiple simulated environments or "virtual" resources from a single, physical hardware system. It involves using software to create an abstraction layer over physical hardware, enabling the creation of virtual machines (VMs) or virtual resources like storage, networks, and servers.

## Cloud models

- `Private Cloud`
  
  A private cloud is a cloud environment that is exclusively used by a single organization. It can be hosted on-premises in the organization's own data center or by a third-party provider.

- `Public Cloud`
  
   A public cloud is a cloud environment where resources and services are made available to multiple organizations (or the general public) over the internet by a third-party provider (such as AWS, Microsoft Azure, or Google Cloud).

- `Hybrid Cloud`
  
  A hybrid cloud combines elements of both private and public clouds, allowing data and applications to be shared between them. This provides greater flexibility and optimization by balancing workloads across both environments.


**`VPN`**

VPN is more like a secure bridge between the user's device and the internet, rather than an intermediary between two users.


## Cloud Service Model

- Software as a Service (`SaaS`)
  
  SaaS provides software applications over the internet on a subscription basis. The software is hosted and maintained by a third-party provider and accessed through a web browser or application.

- Platform as a Service (`PaaS`)
  
  PaaS provides a platform allowing developers to build, deploy, and manage applications without dealing with the underlying infrastructure. It offers a complete development and deployment environment.

- Infrastructure as a Service (`IaaS`)
  
   IaaS provides virtualized computing resources over the internet. It offers fundamental infrastructure components such as virtual machines, storage, and networks on a pay-as-you-go basis.

<p align = "center">
<img src = "../images/cloudServiceModels.png" alt = "alt-text" width = "500">
</p>

## AWS Desgin Principles

###  Operational Excellence 
- use automation whenever possible
- Monitor and track everything
- Continuous improvement

### Security
- use least privilege access 
- Use Multifactor Authentication(MFA)
- Use IAM(Identity & Access Management)
- Protect data in-transit and at rest.
- Monitor and audit continuosly

### Reliability
- Implement Disaster Recovery techniques
- Make use of Autoscaling
- Test and validate regularly
  
### Performance Efficiency
- Choose the right tool for the job
- 