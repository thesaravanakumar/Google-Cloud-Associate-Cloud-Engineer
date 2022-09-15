## Introducing Google Cloud

- Select two fundamental characteristics of cloud computing from this list.

  * [ ] Customers are required to commit to multi-year contracts.
  * [ ] Providers always dedicate physical resources to each customer.
  * [x] Resources are available from anywhere over the network.
  * [ ] All resources are open source.
  * [x] Customers can scale their resource use up and down.

- Which one of the following statements is true regarding the ability to scale cloud computing resources up and down?

  * [ ] Only CPU and memory resources are elastic.
  * [ ] Only storage resources are elastic.
  * [x] CPU, memory, and storage resources are elastic.
  * [ ] Cloud computing does not provide a way to scale resources. 

- What cloud computing service binds application code to libraries that give access to the infrastructure an application needs?

  * [ ] Hybrid cloud
  * [ ] Software as a service
  * [ ] Virtualized data centers
  * [x] Platform as a service
  * [ ] Infrastructure as a service

- What cloud computing service provides raw compute, storage, and network resources that are organized similarly to physical data centers?

  * [ ] Platform as a service
  * [x] Infrastructure as a service
  * [ ] Database as a service
  * [ ] Software as a service

- Why might a Google Cloud customer use resources in several zones within a region?

  * [ ] For better performance
  * [ ] For getting discounts on other zones
  * [x] For improved fault tolerance
  * [ ] For expanding services to customers in new areas

- Who benefits the most from billing by the second for cloud resources, such as virtual machines?

  * [ ] Customers who create virtual machines that run commercially licensed operating systems
  * [ ] Customers who create many virtual machines and leave them running for months
  * [ ] Customers who create too few virtual machines to get discounts
  * [x] Customers who create and run many virtual machines

## Resources and Access in Google Cloud
- When would you choose to have an organization node? (Select two)

  * [x] When you want to create folders
  * [ ] When you want to organize resources into projects
  * [x] When you want to centrally apply organization-wide policies
  * [ ] There’s no choice; organization nodes are mandatory.

- Which statement best describes how Google Cloud resources are associated within the resource hierarchy?

  * [x] All Google Cloud resources are associated with a project.
  * [ ] All Google Cloud resources are associated with a folder.
  * [ ] All Google Cloud resources are associated with an organization.
  * [ ] Google Cloud resources are not associated with the resource hierarchy.

- Consider a single hierarchy of Google Cloud resources. Which of these situations is possible? (Choose 3 responses.)

  * [x] There is no organization node, and there are no folders.
  * [ ] There is no organization node, but there is at least one folder.
  * [x] There is an organization node, and there are no folders.
  * [x] There is an organization node, and there is at least one folder.
  * [ ] There are two or more organization nodes.

- Your company has two Google Cloud projects and you want them to share policies. What is the least error-prone way to set this up?

  * [ ] Duplicate all the policies from one project onto the other. 
  * [x] Place both projects into a folder, and define the policies on that folder.
  * [ ] Create shared resource policies on the common resources that are used in both projects.
  * [ ] Define the new shared policy in the organization node.

- What is the difference between Identity and Access Management (IAM) basic roles and IAM predefined roles?

  * [ ] Basic roles only apply to the owner of the Google Cloud project. Predefined roles can be associated with any user. 
  * [x] Basic roles affect all resources in a Google Cloud project. Predefined roles apply to a specific service in a project.
  * [ ] Basic roles can only be granted to single users. Predefined roles can be associated with a group.
  * [ ] Basic roles only allow viewing, creating, and deleting resources. Predefined roles allow any modification.

- Select the option that displays IAM roles from general to specific. 

  * [x] Basic roles, predefined roles, custom roles
  * [ ] Custom roles, predefined roles, basic roles
  * [ ] Predefined roles, custom roles, basic roles

- How does the resource hierarchy control how IAM policies are inherited?

  * [ ] IAM policies that are implemented higher in the resource hierarchy deny access that is granted by lower-level policies.
  * [x] IAM policies that are implemented by lower-level policies can override the policies defined at a higher level. 
  * [ ] IAM policies are only implemented at the project level; they cannot be amended by lower levels of the resource hierarchy. 

- Which way of accessing Google Cloud lets you control services through the code you write?

  * [ ] The Cloud Console
  * [ ] The Cloud SDK and Cloud Shell
  * [x] APIs
  * [ ] The Cloud Console mobile app

## Virtual Machines and Networks in the Cloud
- Which term describes a secure, individual, private cloud-computing model hosted within a public cloud?

  * [x] Virtual private cloud (VPC)
  * [ ] Virtual private network (VPN)
  * [ ] Content delivery network (CDN)
  * [ ] Domain name system (DNS)

- Select the true statement about Google’s VPC networks and subnets.

  * [x] Networks are global, and subnets are regional.
  * [ ] Both networks and subnets are global.
  * [ ] Networks are regional, and subnets are zonal.
  * [ ] Networks are global, and subnets are zonal.

- An application running in a Compute Engine virtual machine needs high-performance scratch space. Which type of storage meets this need?

  * [x] Local SSD
  * [ ] Zonal persistent disk
  * [ ] Regional persistent disk
  * [ ] Cloud Storage bucket

- Preemptible VMs can offer advantages over a standard Compute Engine VM. What is a reason customers choose preemptible VMs?

  * [ ] To improve performance
  * [x] To reduce cost
  * [ ] To use custom machine types
  * [ ] To reduce cost on premium operating systems

- Which statement best describes how VPC routers and firewalls work?

  * [x] They are managed by Google as a built-in feature.
  * [ ] Customers provision virtual machines and run their routers and firewalls in them.
  * [ ] They are managed by Google in virtual machines and customers can tune or deactivate them.
  * [ ] They are managed by Google in virtual machines and customers cannot modify them.

- A Google Cloud customer wants to load-balance traffic among the backend VMs that form part of a multi-tier application. Which load-balancing option should this customer choose?

  * [ ] The regional load balancer
  * [x] The regional internal load balancer
  * [ ] The global HTTP(S) load balancer
  * [ ] The global TCP proxy
  * [ ] The global SSL proxy

- Which interconnect option is a service level agreement (SLA) available for?

  * [x] Dedicated Interconnect
  * [ ] VPNs with Cloud Router
  * [ ] Direct Peering
  * [ ] Carrier Peering

## Storage in the Cloud
- Which statement describes the correct Cloud Storage use case?

  * [ ] Cloud Storage provides the root file system of a Linux virtual machine. 
  * [x] Cloud Storage provides durable and highly available object storage.
  * [ ] Cloud Storage provides data warehousing services.
  * [ ] Cloud Storage provides RDBMS (Relational Database Management System) services.

- Why would a customer consider the Coldline Storage class?

  * [x] To save money on storing infrequently accessed data
  * [ ] To use the Coldline Storage API
  * [ ] To save money on storing frequently accessed data
  * [ ] To improve security

- Which database service can scale to higher database sizes?

  * [ ] Cloud SQL
  * [x] Cloud Spanner
  * [ ] Bigtable
  * [ ] Firestore

- How are Firestore and Bigtable alike? (Select two answers.)

  * [x] They are both highly scalable.
  * [ ] They both offer SQL-like queries.
  * [x] They are both NoSQL databases.
  * [ ] They both have a free daily quota.

- You manufacture devices with sensors and need to stream huge amounts of data from these devices to a storage option in the cloud. Which storage option is the best choice for your application?

  * [ ] Firestore
  * [x] Bigtable
  * [ ] Cloud Spanner
  * [ ] BigQuery

- Your application needs to store data with strong transactional consistency, and you want seamless scaling up. Which storage option is the best choice for your application?

  * [ ] Firestore
  * [ ] Cloud SQL
  * [x] Cloud Spanner
  * [ ] Cloud Storage

## Containers in the Cloud

- Select two reasons for using containers to deploy applications. (Choose 2 responses.)

  * [x] It creates consistency across development, testing, and production environments.
  * [ ] It provides tight coupling between applications and operating systems.
  * [ ] Allocating resources in which to run containers is not necessary.
  * [x] Migrating workloads is simpler.

- How do containers access an operating system?

  * [ ] Each container has its own instance of an operating system.
  * [x] Containers use a shared base operating system stored in a shared kernel layer.
  * [ ] Containers use a shared base operating system stored in a Cloud Storage bucket.
  * [ ] Containers use a shared base operating system stored in a shared runtime layer.

- What is a Kubernetes pod?

  * [x] A group of containers
  * [ ] A group of VMs
  * [ ] A group of clusters
  * [ ] A group of nodes

- What is a Kubernetes cluster?

  * [ ] A group of pods that manage the administration of a Kubernetes application.
  * [ ] A group of containers that provide high availability for applications.
  * [x] A group of machines where Kubernetes can schedule workloads.

- Where do the resources used to build Google Kubernetes Engine clusters come from?

  * [ ] App Engine
  * [ ] Bare metal servers
  * [x] Compute Engine
  * [ ] Cloud Storage

- How do you keep your Kubernetes version updated in Google Kubernetes Engine? 

  * [ ] You cannot update a running cluster. You need to create a copy of the cluster with the updated Kubernetes version.
  * [x] The Google Kubernetes Engine team periodically performs automatic upgrades of your cluster to newer stable versions.
  * [ ] You need to stop your cluster and manually update the Kubernetes version in your cluster.
  * [ ] You are required to set up a cron job to periodically check the Kubernetes version in your cluster.

- Anthos provides a rich set of tools for monitoring and maintaining the consistency of your applications across which of the following locations?

  * [ ] Applications hosted on-premises only.
  * [ ] Applications hosted with one cloud provider only.
  * [ ] Applications hosted with multiple cloud providers only.
  * [x] Applications hosted on-premises, in the cloud, or in multiple clouds.

## Applications in the Cloud

- App Engine is best suited to the development and hosting of which type of application?
  * [ ] Applications that require at least one instance running at all times.
  * [x] A web application 
  * [ ] A long-running batch processing application
  * [ ] Applications that require full control of the hardware they are running on

- Which statements are true about App Engine? (Select 2).

  * [x] App Engine manages the hardware and networking infrastructure required to run your code. 
  * [ ] App Engine charges you based on the resources you preallocate instead of the resources you use.
  * [ ] Developers who write for App Engine do not need to code their applications in any particular way to use the service.
  * [ ] App Engine requires you to supply or code your own application load balancing and logging services.
  * [x] The daily billing for an App Engine application can drop to zero.

- What are the advantages of using App Engine’s flexible environment instead of its standard environment? (Select 3).

  * [x] You can install third-party binaries.
  * [ ] Google provides automatic in-place security patches.
  * [x] Your application can write to the local disk.
  * [ ] Your application can execute code in background threads.
  * [x] You can use SSH to connect to the virtual machines on which your application runs.

- Which Google Cloud service should you choose to perform business analytics and billing on a customer-facing API?

  * [ ] Cloud Run API
  * [x] Apigee Edge
  * [ ] Cloud Endpoints
  * [ ] Compute Engine API

- Select the managed compute platform that lets you run stateless containers through web requests or Pub/Sub events.

  * [ ] Apigee Edge
  * [ ] Cloud Endpoints
  * [ ] Cloud Source Repositories
  * [x] Cloud Run

- Cloud Run can only pull images from: 

  * [x] Artifact Registry
  * [ ] Docker Hub
  * [ ] Self-hosted registries
  * [ ] GitHub

## Developing and Deploying in the Cloud

- Why would a developer choose to store source code in Cloud Source Repositories? (Select 2)

  * [x] To reduce work
  * [ ] To have total control over the hosting infrastructure
  * [x] To keep code private to a Google Cloud project
  * [ ] It is the only way to access your source code in a repository.

- Why might a Google Cloud customer choose to use Cloud Functions?

  * [ ] Their application has a legacy monolithic structure that they want to separate into microservices.
  * [ ] Cloud Functions is a free service for hosting compute operations.
  * [ ] Cloud Functions is the primary way to run Node.js applications in Google Cloud.
  * [x] Their application contains event-driven code that they don't want to provision compute resources for.

- Select the advantage of putting the event-driven components of your application into Cloud Functions.

  * [ ] Cloud Functions eliminates the need to use a separate service to trigger application events.
  * [x] Cloud Functions handles scaling these components seamlessly.
  * [ ] In Cloud Functions, code can be written in C# or C++.
  * [ ] In Cloud Functions, processing is always free of charge.

- Why might a Google Cloud customer choose to use Terraform?

  * [ ] Terraform can be used as an infrastructure management system for Kubernetes pods.
  * [ ] Terraform can be used to enforce maximum resource utilization and spending limits on your Google Cloud resources.
  * [ ] Terraform can be used as a version-control system for your Google Cloud infrastructure layout.
  * [x] Terraform can be used as an infrastructure management system for Google Cloud resources.

## Logging and Monitoring in the Cloud

- There are “Four Golden Signals” that measure a system’s performance and reliability. What are they?

  * [ ] Availability, durability, scalability, resiliency
  * [ ] Latency, traffic, saturation, errors
  * [ ] Get, post, put, delete
  * [ ] KPIs, SLIs, SLOs, SLAs

- Which definition best describes a service level indicator (SLI)? 

  * [ ] A time-bound measurable attribute of a service
  * [ ] A percentage goal of a measure you intend your service to achieve
  * [ ] A contract with your customers regarding service performance
  * [ ] A key performance indicator; for example, clicks per session or customer signups

- Which option describes a commitment made to your customers that your systems and applications will have only a certain amount of “downtime”?

  * [ ] Service level indicator
  * [ ] Service level objective
  * [ ] Key performance indicator
  * [ ] Service level agreement

- You want to create alerts on your Google Cloud resources, such as when health checks fail. Which is the best Google Cloud product to use?

  * [ ] Cloud Debugger 
  * [ ] Cloud Monitoring
  * [ ] Cloud Functions
  * [ ] Cloud Trace

- Select the two correct statements about Cloud Logging.

  * [ ] Cloud Logging lets you define metrics based on your logs.
  * [ ] Cloud Logging requires the use of a third-party monitoring agent.
  * [ ] Cloud Logging requires you to store your logs in BigQuery or Cloud Storage.
  * [ ] Cloud Logging lets you view logs from your applications and filter and search on them.
  * [ ] Cloud Logging lets you define uptime checks.
