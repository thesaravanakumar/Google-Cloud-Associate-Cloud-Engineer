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
