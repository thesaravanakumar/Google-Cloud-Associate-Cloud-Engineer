## Google Cloud Fundamentals: Core Infrastructure

**Goal:** ```To provide an overview of Google Cloud```

<p align="center">
<img align="center" width="870" src="https://user-images.githubusercontent.com/59575502/189478413-27a54684-5577-411d-a78f-dc1e251770fa.png">
</p>

</br>
 
By the end of this course, you should be able to, 
- Identify the purpose and value of Google Cloud products and services.
- Choose among and use application deployment environments on Google Cloud, like App Engine, Google Kubernetes Engine, and Compute Engine
- Choose among and use Google Cloud Storage options like Cloud Storage, Cloud SQL, Cloud Bigtable, and Firestore
- Interact with Google Cloud services.
- Describe ways in which customers have used Google Cloud.

<img align="right" src="https://user-images.githubusercontent.com/59575502/189479146-7b131338-4801-4aba-86c6-3f98b9e8c81b.jpeg">

### Cloud computing overview


The ```US National Institute of Standards and Technology``` created the term ```cloud computing``` 
</br>
</br>
**Cloud Computing:**
</br>
- Deliver a service to a network using hardware and software. Anyone with internet can access it.
- Way of using IT and that has 5 traits,
```
  - Customers get computing resources that are on-demand and self-service.
  - Customers get access to those resources over the Internet from anywhere they have a connection.
  - The cloud provider has a big pool of those resources and allocates them to users out of that pool.
  - The resources are elastic, which means they're flexible, so customers can be.
  - Customers pay only for what they use or reserve as they go.
  ```
**Three** main categories of cloud computing:
- ```Infrastructure as a Service``` ( Compute, Storage, Networks )
  - Organized virtually into resources that are similar to physical data centers.
  - Pay for what they allocate.
- ```Platform as a Service```
  - Cloud environment that has everything developers need to build, run, and manage applications. No need to maintain software development platform.
  - Pay for what they use.
- ```Software as a Service```( Gmail, Docs )
  - Not installed in local system.
  - They run in cloud as a service ( can consume directly )

### **Regions** 

Google Cloud’s infrastructure is based in five major geographic locations: **North America, South America, Europe, Asia, and Australia.**
**Example Region:** ```europe-west2``` </br>
**Zones:** ```europe-west2-a, europe-west2-b, europe-west2-c``` </br>
>check current location status [here](https://cloud.google.com/about/locations).

<p align="center">
<img align="center" src="https://user-images.githubusercontent.com/59575502/189482754-b8f6715e-8f9e-443d-bcfb-e916ffcc08d9.png">
</p>

### Google Cloud Resource Hierarchy
<img align="left" width="400" src="https://user-images.githubusercontent.com/59575502/189484177-7f6680fa-539a-4b99-a4bd-25515c5316ee.png">

- Policies can be defined at the project, folder, and organization node levels. Some Google Cloud services allow policies to be applied to individual resources, too.
- Policies are also inherited downward. ( If you apply a policy to a folder, it will also apply to all of the projects within that folder )
- To use a folder you need an organizational node.

<img width="400" align="right" src="https://user-images.githubusercontent.com/59575502/189485222-2b12ceb1-2d25-4034-a78b-ab494c489d2a.png">

</br></br></br></br></br></br></br></br></br></br>
### Identity and Access Management (IAM)

- Administrators can apply policies that define who can do what on which resources.
- An IAM role is a collection of permissions.
- There are **three** roles in IAM
  - Basic Cloud IAM role ( owner, editor, viewer, billing admin )
  - Predefined Cloud IAM role ( Instance Admin role - For compute engine access )
  - Custom Cloud IAM role ( create your own ) -> ```not for folder level```

### Service accounts

What if you want to give permissions to a Compute Engine virtual machine, rather than to a person?
- It's a ```resource``` so you can add it to IAM.
- Service accounts are named with an email address
- Instead of passwords they use cryptographic keys to access resources.

### Cloud Identity

- Give users easy access to apps with single sign-on
- Multi-factor authentication protects user and company data
- Usage of Active Directory or LDAP ( If anyone joins/leaves the org )

### Interacting with Google Cloud
- Cloud Console
- Cloud SDK in Cloud Shell ( ```gcloud```, ```gsutil``` for cloud storage, ```bq``` for big query )
- APIs ([Google APIs Explorer](https://developers.google.com/apis-explorer))
- Cloud Console Mobile App

### Cloud Shell 
- Provides command line access to Cloud resources directly from a browser.
- ```Debian-based``` virtual machine with a ```persistent five gigabyte``` home directory (makes it easy to manage Google Cloud Projects and Resources)
- With Cloud Shell, the Cloud SDK, gcloud command, and other utilities are always installed, available up to date, and fully authenticated.

---
### Virtual Private Cloud Networking
#### Virtual Private Cloud ( virtual version of a physical network ):
A VPC ( a foundation for your network in the cloud ) is a secure individual private cloud computing model hosted within a public cloud that provides **managed network functionality**.
It has a ```global-scope``` so it can reach anywhere ( spans evey regions without accessing public internet ) securely.

<img align = "left" width="600" src="https://user-images.githubusercontent.com/59575502/189604433-09b39179-ae3b-4958-9753-f1a746bf49a4.png">

- Customers can run code, store data, host websites and do anything else they could do in an ordinary private cloud.
- This private cloud is hosted remotely by a public cloud provider.
- VPC's combine the scalability and convenience of public cloud computing with the data isolation of private cloud computing.
- Networks are **global**, and subnets are **regional**.

</br>

```subnet``` is a fancy way of saying an IP segment in a VPC, In VPC ```routing tables``` are built-in so you don’t have to provision or manage a router. 
### VPC Peering
With VPC Peering, a relationship between two VPCs can be established to exchange traffic. Alternatively, to use the full power of **Identity Access Management (IAM)** to control who and what in one project can interact with a VPC in another, you can configure a ```Shared VPC```.
**The resources that can be using a VPC network are the following:**
- Shared VPC
- Interconnect
- NAT
- Firewall Rules
- Cloud Router
- VPC Peering
- VPN
- Subnets, Instances and IP ranges


### Compute Engine
Compute Engine provides machine type recommendations to help you optimize the resource utilization of your virtual machine (VM) instances.
- create and run ```VM``` on Google infrastructure and has ```Auto-scaling```.
- There are no upfront investments.
- VM contains the power and functionality of a full-fledged **operating system**.
- Compute Engine has permission to ```terminate a job``` if its resources are needed elsewhere.

### Cloud Load Balancing

<p align="center">
<img width="600" align = "center" src="https://user-images.githubusercontent.com/59575502/189662628-2f54b6e8-b77f-416e-9821-29ba138cfae8.png">
</p>

The job of a load balancer is to distribute user traffic across multiple instances of an application. Cloud Load Balancing is a fully distributed, software-defined, managed service for all your traffic. The load balancers ```don’t run in VMs``` that you have to manage, you don’t have to worry about scaling or managing them. You can put Cloud Load Balancing in front of all of your traffic.
Types of LB's
- ```Global HTTP(S)``` -> For cross-regional load balancing for a web application
- ```Global SSL Proxy``` -> For Secure Sockets Layer traffic that is not HTTP, use the Global SSL Proxy load balancer
- ```Global TCP Proxy``` -> If it’s other TCP traffic that doesn’t use SSL
- ```Regional``` -> You can still load balance across a Google Cloud region with the Regional load balancer
- ```Regional Internal``` -> If you want to load balance traffic inside your project
> Those last two proxy services only work for specific port numbers, and they only work for TCP

### Cloud DNS and Cloud CDN
DNS [(8.8.8.8)](https://dns.google/) is what translates Internet host names to addresses.
**Cloud DNS** lets you publish your zones and records in DNS without the burden of managing your own DNS servers and software. It offers both ```public zones``` and ```private``` managed DNS zones.

```Edge caching``` refers to the use of caching servers to store content closer to end users. 
Cloud **C**ontent **D**elivery **N**etwork ( To accelerate content delivery in your application ) 

### Connecting networks to Google VPC
<p align="center">
<img width="600" src="https://user-images.githubusercontent.com/59575502/189668789-a260eda3-3d46-49d1-882e-8c474c419846.png">
</p>

- ```IPsec VPN Protocol``` -> VPN over the Internet and use the IPsec VPN protocol to create a tunnel connection
- ```Direct Peering``` -> Putting a router in the same public data center as a google point of presence
- ```Carrier Peering``` -> Gives you direct access from your on-premises network, through a service provider's network to google
- ```Dedicated Interconnect``` -> Provides direct physical connections between your on-premises network and Google's network
- ```Partner Interconnect``` -> Useful if a data center is in a physical location that can't reach a Dedicated Interconnect co location facility.

---

### Google Cloud storage options
<img align = "right" width="600" src="https://user-images.githubusercontent.com/59575502/189676020-586630d9-716d-4748-a92f-a964d41f32dd.png">

#### Cloud Storage ( object storage product )
- Object storage for companies of all sizes. Store any amount of data. Retrieve it as often as you’d like.
- Immutable and ```object versioning``` ( a new version is made with every change ) 
- **Access Control Lists** (ACLs) = scope + permissions
- **Lifecycle policies** (delete when you want)
- **Advantages:**
  - Unlimited storage
  - Worldwide accessibility (geo-redundancy)
  - Low latency and high durability.
  - **HTTPS/TLS** security on server-side

#### Types of storage classes: 
- [Standard Storage](https://cloud.google.com/storage/docs/storage-classes#standard): Good for “hot” data that’s accessed frequently, including websites, streaming videos, and mobile apps.
- [Nearline Storage](https://cloud.google.com/storage/docs/storage-classes#nearline): Low cost. Good for data that can be stored for at least 30 days, including data backup and long-tail multimedia content.
- [Coldline Storage](https://cloud.google.com/storage/docs/storage-classes#coldline): Very low cost. Good for data that can be stored for at least 90 days, including disaster recovery.
- [Archive Storage](https://cloud.google.com/storage/docs/storage-classes#archive): Lowest cost. Good for data that can be stored for at least 365 days, including regulatory archives.


#### Cloud SQL
Cloud SQL offers fully managed relational databases, including MySQL, PostgreSQL, and SQL Server as a service.

<p align="center">
<img width="1000" src="https://user-images.githubusercontent.com/59575502/189688026-0878691d-61a0-4ff1-8af2-94c2f2bfa126.png">
</p>


#### Cloud Spanner
Cloud Spanner is a fully managed relational database service that scales horizontally, is strongly consistent, and speak SQL. Battle tested by Google's own mission critical applications and services, Spanner is the service that powers Google's $80 billion business.

<p align="center">
<img width="1000" src="https://user-images.githubusercontent.com/59575502/189688386-40616eb5-70e4-4f7e-be16-c4481bd4191e.png">
</p>


#### Firestore
Firestore is a flexible, horizontally scalable, ```NoSQL``` cloud database for mobile, web, and server development. With Firestore, data is stored in documents and then organized into collections. Documents can contain complex nested objects in addition to subcollections. Firestore’s NoSQL queries can then be used to retrieve individual, specific documents or to retrieve all the documents in a collection that match your query parameters. Queries can include multiple, chained filters and combine filtering and sorting options. 

#### Cloud Bigtable

Cloud Bigtable is Google's NoSQL Big data database service. Bigtable is designed to handle massive workloads at consistent low latency and high throughput. So it's a great choice for both operational and analytical applications including internet of things, user analytics, and financial data analysis.

<p align="center">
<img width="1200" src="https://user-images.githubusercontent.com/59575502/189877918-42ff8119-2938-4b76-a35c-31fc4d25f9df.png">
</p>

---
### Introduction to containers

<p align="center">
<img width="1200" src="https://user-images.githubusercontent.com/59575502/189879270-586bc06d-1084-477b-be2c-39f5c384981c.jpg">
</p>
A Pod is the smallest unit in Kubernetes that you can create or deploy. It represents a running process on your cluster as either a component of replication or an entire app.

- ```kubectl run``` -> Starts a deployment with a container running inside a Pod.
- ```kubectl get pods``` -> List of the running pods in a project.
- ```kubectl scale``` -> To scale of deployment.
- ```kubectl get services``` -> To get the external IP of the service
- ```kubectl rollout, kubectl apply``` -> Update your container

### Google Kubernetes Engine
GKE is a Google-hosted managed Kubernetes service in the Cloud.
```gcloud container clusters create k1``` -> To start up kubernetes is on a cluster in GKE.

<p align="center">
 <img width="1200" src="https://user-images.githubusercontent.com/59575502/189883468-98e9f52e-9746-4a6f-b28d-8001ea12b95f.jpg">
</p>

### Anthos

<img align = "left" width="600" src="https://user-images.githubusercontent.com/59575502/189885982-03b1576b-fcff-4be6-9bc2-a6111e834361.png">

- Anthos is a ```hybrid and multi cloud``` solution powered by the latest innovations in distributed systems and service management software from Google.
- The Anthos framework rests on ```Kubernetes``` and ```GKE On-Prem```.
- Anthos also provides a rich set of tools for ```monitoring and maintaining``` the consistency of your applications across all of your network, whether on premises in the cloud or in multiple clouds.

### Development in the cloud
#### Cloud Source Repositories
Cloud Source Repositories provides full featured Git repositories hosted on Google Cloud that support the collaborative development of any application or service, including those that run on App Engine and Compute Engine. With Cloud Source Repositories, you can have any number of private Git repositories.

<img width="600" height="250" align = "right" src="https://user-images.githubusercontent.com/59575502/189898777-d10b12c8-f62c-4025-b9cf-40fb7f3519da.png">

#### Cloud Functions
- Event driven serverless compute platform.
- Scales automatically.
- Cloud Functions allows you to **trigger** your code from Google Cloud, Firebase, and Google Assistant, or call it directly from any web, mobile, or backend application via HTTP. You are only billed for your function's execution time, metered to the nearest 100 milliseconds. You pay nothing when your function is idle.

### Applications in the cloud
#### App Engine
- App Engine is a cloud computing platform as a service, fully managed, serverless platform for developing and hosting web applications in Google-managed data centers at scale. 
- Applications are sandboxed and run across multiple servers. With App Engine, there are no servers to provision or maintain. 
- Lets app developers build scalable web and mobile back ends in any programming language on a fully managed serverless platform.

There are two types of [App Engine environments](https://cloud.google.com/appengine/docs/the-appengine-environments), ```standard``` and ```flexible``` 

<p align="center">
<img width="1200" src="https://user-images.githubusercontent.com/59575502/191241036-484de5cd-6bb9-4978-ade8-a3e2db062e83.png">
<img width="600" align="right" src="https://user-images.githubusercontent.com/59575502/191240058-785474cd-8e29-4b1d-99fa-a1d980594195.png">
</p>

#### Google Cloud API management tools
- Cloud Endpoints
- Apigee Edge

</br> 
</br> 

> Backend services for Apigee Edge don't have to be in Google Cloud. As a result, engineers also often use it to take apart legacy applications. Instead of replacing a large important application in one move, they can use Apigee Edge to peel off its services individually instead. This allows them to stand up microservices to implement each in turn until the legacy application can finally be retired

<p align="center">
 <img width="1200" src="https://user-images.githubusercontent.com/59575502/191251989-00f56449-e825-4b46-abd1-84d185e676d2.png">
</p>

#### Cloud Run

<p align="center">
<img width="1200" src="https://user-images.githubusercontent.com/59575502/191254270-18bd34ba-8455-4c86-a30b-0b9ad0834e3c.png">
</p>

- Can allocate up to ```four vCPUs``` and ```eight gigabytes of memory```
- Once you've deployed your container image, you'll get a unique ```HTTPS URL``` back. Cloud Run then starts your container on demand to handle requests, and ensures that all incoming requests are handled by **dynamically adding and removing containers**
- With Cloud Run, You can use a ```container-based``` workflow as well as a ```source-based``` workflow. </br>
```Buildpacks``` -> Cloud Run then builds your source and packages the application into a container image for you

### Logging and Monitoring in the Cloud
There are **four golden signals** that measure a system's performance and reliability.
- ```Latency``` -> measures how long it takes a particular part of a system to return a result.
- ```Traffic``` -> measures how many requests are reaching your system.
- ```Saturation``` -> measures how close to capacity a system is.
- ```Errors``` -> measure system failures or other issues.

Types of **targets** set for systems four golden signals metrics. 
- ```Service level indicators (SLI)``` -> carefully selected monitoring metrics that measure one aspect of a services reliability.
- ```Service level objective (SLO)``` -> combines a service level indicator with a target reliability. 
- ```Service-level agreements (SLA)``` -> commitments made to your customers that your systems and applications will only have a certain amount of downtime.
