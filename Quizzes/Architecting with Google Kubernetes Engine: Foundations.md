## Cloud Computing and Google Cloud

- Which statements are true about cloud computing? Mark all that are true (2 correct answers).

  * [x] Customers who need more resources can get them rapidly
  * [x] Customers pay for the resources they use or reserve.
  * [ ] Cloud computing providers dedicate particular physical resources to particular customers.
  * [ ] Human intervention is required to stop using cloud resources once reserved, and payment continues until the change is confirmed.

- Which of these Google Cloud compute services provides environments for execution of code, in which users don't have to worry about infrastructure management? Choose all that are correct (2 correct answers).

  * [x] Cloud Functions
  * [ ] Compute Engine
  * [ ] Google Kubernetes Engine
  * [x] App Engine

## Resource Management
- Within which of these Google Cloud geographic scopes are network latencies generally less than 1 millisecond? Choose all that are correct (2 correct answers).

  * [x] Region
  * [ ] Multi-Region
  * [ ] Global
  * [x] Zone

- What type of resource is a Compute Engine virtual machine?

  * [x] Zonal
  * [ ] Regional
  * [ ] Multi-regional
  * [ ] Global

- What is the base-level organizing entity for creating and using Google Cloud resources and services?

  * [x] Project
  * [ ] Region
  * [ ] Cluster
  * [ ] Folder

## Billing

- At what level in the Google Cloud resource hierarchy is billing set up?

  * [x] Project
  * [ ] Folder
  * [ ] Organization
  * [ ] Individual users

- Which type of quota resets at regular intervals?

  * [x] Rate quotas
  * [ ] Allocation quotas

## Interacting with Google Cloud

- Which of these ways to interact with give you access to the gcloud and kubectl commands? Choose all that are correct (2 correct answers).

  * [x] Cloud Shell
  * [x] Cloud SDK
  * [ ] Console
  * [ ] Cloud Console mobile app

## Introduction to Google Cloud

- You are considering deploying a solution using containers on Google Cloud. What Google Cloud solutions are available to you that will provide a managed compute platform with native support for containers?

   * [ ] Compute Engine Autoscaling Groups
   * [x] Google Kubernetes Engine Clusters
   * [ ] Container Registry
   * [ ] Cloud Functions

- You are ready to start work building an application in Google Cloud. What IAM hierarchy should you implement for this project?

   * [ ] Create new projects for each of the component applications and create folders inside those for the resources.
   * [ ] Create new projects and resources inside departmental folders for the resources needed by the component applications.
   * [ ] Create a new folder inside your organization and create projects inside that folder for the resources.
   * [x] Create a new organization for the project and create all projects and resources inside the new organization.

- You are developing a new product for a customer and need to implement control structures in Google Cloud to help manage the Google Cloud resources consumed by the product and the billing for the customer account. What steps should you take to manage costs for this product and customer?

   * [ ] Configure the billing account for each project associated with the product.
   * [ ] Set up budgets and alerts at the project level for the product.
   * [x] Configure the billing account at the product folder level in the resource hierarchy.
   * [ ] Configure quotas and limits for the product folders.

- You need to write some automated scripts to run periodic updates to the resources in your Google Cloud environment. What tools can you install in your own computers to allow you to run those scripts?

   * [ ] The Google Cloud Console
   * [ ] The Cloud Console Mobile app
   * [x] The Cloud SDK
   * [ ] The Cloud Shell

- One of the key characteristics of cloud computing is the concept of measured service. What is the primary customer benefit of the measured service aspect of cloud computing?

   * [ ] You can get more resources as quickly as you need them.
   * [ ] Resources can be allocated automatically.
   * [x] You pay only for the resources you consume.
   * [ ] You share resources from a large pool enabling economies of scale.

## Introduction to Containers

- Which of these problems are containers intended to solve? Mark all that are correct (3 correct answers),

   * [x] Applications need a way to isolate their dependencies from one another.
   * [ ] Large monolithic applications that need to be run in the cloud.
   * [x] Packaging applications in virtual machines can be wasteful.
   * [x] It's difficult to troubleshoot applications when they work on a developer's laptop but fail in production.

## Containers and Container Images

- Why do Linux containers use union file systems?

   * [ ] To control an application's ability to see parts of the directory tree and IP addresses
   * [ ] To control an application's maximum consumption of CPU time and memory
   * [x] To efficiently encapsulate applications and their dependencies into a set of clean, minimal layers
   * [ ] To give a container its own virtual memory address space

- What is significant about the topmost layer in a container? Choose all that are true (2 correct answers).

   * [ ] Reading from or writing to the topmost layer requires special software libraries.
   * [ ] Reading from or writing to the topmost layer requires special privileges.
   * [x] The topmost layer's contents are ephemeral. When the container is deleted, the contents will be lost.
   * [x] An application running in a container can only modify the topmost layer.

## Introduction to Kubernetes

- When you use Kubernetes, you describe the desired state you want, and Kubernetes's job is to make the deployed system conform to your desired state and to keep it there in spite of failures. What is the name for this management approach?

   * [ ] Virtualization
   * [ ] Imperative configuration
   * [ ] Containerization
   * [x] Declarative configuration

- What is a stateful application?

   * [ ] A web front end
   * [ ] An application that is not containerized
   * [x] An application that requires user and session data to be stored persistently

## Introduction to Google Kubernetes Engine

- What is the relationship between Kubernetes and Google Kubernetes Engine?

   * [ ] Kubernetes and Google Kubernetes Engine are two names for the same thing.
   * [ ] Google Kubernetes Engine is a closed-source variant of Kubernetes.
   * [x] Google Kubernetes Engine is Kubernetes as a managed service.

- What is the name for the computers in a Kubernetes cluster that can run your workloads?

   * [ ] Control Planes
   * [x] Nodes
   * [ ] Container images
   * [ ] Containers

- Which of the following supports scaling a Kubernetes cluster as a whole?

   * [x] Google Kubernetes Engine
   * [ ] Kubernetes
   * [ ] Compute Engine

## Containers and Kubernetes in Google Cloud

- You are choosing a technology for deploying applications, and you want to deliver them in lightweight, standalone, resource-efficient, portable packages. Which choice best meets those goals?

  * [x] Containers
  * [ ] Virtual Machines
  * [ ] Hypervisors
  * [ ] Executable files

- You are classifying a number of your applications into workload types. Select the stateful applications in this list of applications. Choose the TWO responses that are correct.

  * [x] A gaming application that keeps track of user state persistently.
  * [x] A shopping application that saves user shopping cart data between sessions.
  * [ ] Web server front end for your inventory system.
  * [ ] Image recognition application that identifies product defects from images.

- Google Compute Engine provides fine-grained control of costs. Which Compute Engine features provide this level of control? (Choose TWO)

  * [ ] Billing budgets and alerts
  * [ ] Autoscaling groups
  * [ ] Managed instance groups
  * [x] Per-second billing
  * [x] Fully customizable virtual machines

- You are deploying a containerized application, and you want maximum control over how containers are configured and deployed. You want to avoid the operational management overhead of managing a full container cluster environment yourself. Which Google Cloud compute solution should you choose?

  * [ ] App Engine
  * [ ] Cloud Functions
  * [ ] Compute Engine
  * [x] Google Kubernetes Engine

## Kubernetes Concepts

- What is the difference between a pod and a container?

  * [ ] A container contains one or more pods.
  * [ ] Pods and containers are two names for the same thing.
  * [x] A pod contains one or more containers.

## The Kubernetes Control Plane

- Which control plane component is the only one with which clients interact directly?

  * [x] kube-apiserver
  * [ ] etcd
  * [ ] kube-scheduler
  * [ ] kube-controller-manager

- Which control plane component is the cluster's database?

  * [x] etcd
  * [ ] kube-apiserver
  * [ ] kube-scheduler
  * [ ] kube-controller-manager

- What is the role of the kubelet?

  * [x] To serve as Kubernetes’s agent on each node
  * [ ] To maintain network connectivity among the Pods in a cluster
  * [ ] To interact with underlying cloud providers

## Google Kubernetes Engine Concepts

- In GKE clusters, how are nodes provisioned?

  * [x] As Compute Engine virtual machines
  * [ ] As abstract parts of the GKE service that are not exposed to Google Cloud customers

- In GKE, how are control planes provisioned?

  * [ ] As Compute Engine virtual machines
  * [x] As abstract parts of the GKE service that are not exposed to Google Cloud customers

- What is the purpose of configuring a regional cluster in GKE?

  * [x] To allow applications running in the cluster to withstand the loss of a zone
  * [ ] To ensure that the cluster's workloads are isolated from the public Internet

## Kubernetes Object Management

- In a manifest file for a Pod, in which field do you define a container image for the Pod?

  * [x] spec
  * [ ] apiVersion
  * [ ] kind
  * [ ] metadata

- What are Kubernetes namespaces useful for? Choose all that are correct (2 correct answers).

  * [x] Namespaces let you implement resource quotas across your cluster.
  * [x] Namespaces allow you to use object names that would otherwise be duplicates of one another.
  * [ ] Namespaces partition Linux kernel resources. 
  * [ ] Namespaces make resources more secure,

- What is the purpose of the Deployment object?

  * [x] To ensure that a defined set of Pods is running at any given time.
  * [ ] To launch one or more Pods and ensure that a specified number of them successfully run to completion and exit.
  * [ ] To launch one or more Pods on a time-based schedule.

## Kubernetes Controller Objects

- What is the purpose of a Service? Choose all that are true (2 correct answers)

  * [x] To provide a load-balancing network endpoint for Pods
  * [x] To allow you to choose how Pods are exposed
  * [ ] To allow you to put constraints on Pods' resource consumption
  * [ ] To provide a way to inspect and diagnose code running in a Pod

- If you are deploying applications in your Pods that need persistent storage, which controller type should you use?

  * [x] StatefulSet
  * [ ] Deployment
  * [ ] DaemonSet
  * [ ] ReplicaSet

## Kubernetes Architecture

- You are designing an application, and you want to ensure that the containers are located as close to each other as possible, in order to minimize latency. Which design decision helps meet this requirement?

  * [ ] Give the containers the same labels.
  * [ ] Place the containers in the same cluster.
  * [x] Place the containers in the same Pod.
  * [ ] Place the containers in the same Namespace.

- Which Kubernetes component does the kubectl command connect to in order to carry out operations on a cluster?

  * [x] kube-apiserver
  * [ ] kube-scheduler
  * [ ] kube-controller-manager
  * [ ] kube-dns

- You have deployed a new Google Kubernetes Engine regional cluster with four machines in the default pool for the first zone and left the number of zones at the default. How many Compute Engine machines are deployed and billed against your account?

  * [ ] Ten. (Four nodes are deployed in the first zone and three nodes are deployed in two other zones because you selected the defaults.)
  * [x] Twelve. (Four nodes are deployed in each of three zones. A control plane node is deployed in each zone which is indirectly billed against your account through the cluster management fee.)
  * [ ] Fifteen. (Four nodes and a single control plane are deployed to each of the three zones. A control plane node is deployed in each zone and it is billed against your account.)
  * [ ] Sixteen. (Four nodes are deployed in primary and secondary zones in two regions, for a total of 4 zones and 16 nodes. A control plane node is deployed in each zone but it is not billed to your account.)

- You need to ensure that the production applications running on your Kubernetes cluster are not impacted by test and staging deployments. Which features should you implement and configure to ensure that the resources for your production applications can be prioritized?

  * [ ] Configure resource requests for Test, Staging and Production and configure specific Kubernetes resource quotas for the Production Namespace.
  * [ ] Configure Namespaces for Test, Staging and Production and configure specific Kubernetes resource quotas for the Production Namespace.
  * [x] Configure Namespaces for Test, Staging and Production and configure specific Kubernetes resource quotas for the test and staging Namespaces.
  * [ ] Configure labels for Test, Staging and Production and configure specific Kubernetes resource quotas for the Production Namespace.

- When configuring storage for stateful applications, what steps must you take to provide file system storage inside your containers for data from your applications that will not be lost or deleted if your Pods fail or are deleted for any reason?

  * [x] You must create Volumes using network based storage to provide durable storage remote to the Pods and specify these in the Pods.
  * [ ] You must create Volumes using local Storage on the Nodes and mount the Volumes inside your containers to provide durable storage.
  * [ ] You must export the data from your applications to a remote service that preserves your data.
  * [ ] You must mount NFS Volumes on each container in the Pod that requires durable storage.

- You have a new logging and auditing utility that you need to deploy on all of the nodes within your cluster. Which type of controller should you use to handle this task?

  * [ ] StatefulSet
  * [ ] ReplicaSet
  * [x] DaemonSet
  * [ ] Deployment.

- You want to deploy multiple copies of your application, so that you can load balance traffic across them. How should you deploy this application's Pods to the production Namespace in your cluster?

  * [ ] Create separate named Pod manifests for each instance of the application and deploy as many as you need.
  * [ ] Deploy the Pod manifest multiple times until you have achieved the number of replicas required.
  * [x] Create a Deployment manifest that specifies the number of replicas that you want to run.
  * [ ] Create a Service manifest for the LoadBalancer that specifies the number of replicas you want to run.








