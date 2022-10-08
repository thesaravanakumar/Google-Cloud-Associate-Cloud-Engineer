## Architecting with Google Kubernetes Engine: Foundations

### Introduction to Containers
Containers are isolated user spaces for running application code. Containers are lightweight because they don't carry a full operating system, they can be scheduled or packed tightly onto the underlying system, which is very efficient. They can be created and shut down very quickly because you're just starting and stopping the processes that make up the application and not booting up an entire VM and initializing an operating system for each application.

- lightweight
- stand-alone
- resource efficient
- portable execution packages
- no worrying about software dependencies

```Image``` -> An application, and its dependencies are called an image.
```Container``` -> A container is simply running an instance of an image.

#### Docker
Docker is an open source technology that allows you to create and run applications in containers, but it doesn't offer a way to orchestrate those containers at scale as Kubernetes does.

### Computing Options

<div align="center">
  
| **Service name**  | **Description**                                                     |
|:-----------------:|:-------------------------------------------------------------------:|
| Kubernetes Engine | A managed environment for deploying containerized application       |
| Compute Engine    | A managed environment for deploying virtual machines                |
| App Engine        | A managed serverless platform for deploying applications            |
| Cloud Function    |  A managed serverless platform for deploying event-driven functions |

<img width="600" src="https://user-images.githubusercontent.com/59575502/194712648-fd4df9e1-6863-40ee-8c42-0da2e3c27323.png">

<img width="600" src="https://user-images.githubusercontent.com/59575502/194712136-c364b859-e67d-491f-8220-06e99e224c0f.png">
</div>

### How billing works
- Billing account pays for project resources.
- A billing account is linked to one or more projects.
- Charged automatically or invoiced every month or at threshold limit.
- Subaccounts can be used for separate billing for projects.


#### What is Kubernetes?

<img width="201" align="right" src="https://user-images.githubusercontent.com/59575502/194712897-62d2aa47-fc6d-4b62-a412-8553c7af0736.png">

> A software layer that sits between your applications and your hardware infrastructure

Containers are a way to package and run code that's more efficient than virtual machines. Kubernetes provides the tools you need to run containerized applications in production and at scale. </br>

Kubernetes is an open source platform that helps you orchestrate and manage your container infrastructure on-premises or in the Cloud. 
- It's a container-centric management environment. 
- Google originated it and then donated it to the open source community. Now it's a project of the vendor-neutral Cloud Native Computing Foundation. 
- It automates the **deployment, scaling, load balancing, logging, monitoring, and other** management features of containerized applications. 

> Kubernetes supports declarative configurations. ```imperative configuration -> not recommended```

#### What is Google Kubernetes Engine?

- GKE is fully-managed, which means that you don't have to provision the underlying resources. 
- It will help you deploy, manage, and scale Kubernetes environments for your containerized applications on GCP.
- GKE is a component of the GCP compute offerings, it makes it easy to bring your Kubernetes workloads into the cloud.
- GKE uses a container- optimized operating system. These operating systems are maintained by Google. They are optimized to scale quickly and with a minimal resource footprint.

#### Explaining GKE features
- Fully managed
- Container-optimized OS
- Auto upgrade (automatically repair unhealthy nodes)
- Auto repair (it will cause it's workloads to gracefully exit and then recreate that node)
- Cluster scaling
- Seamless integration
- Identity and access management
- Integrated logging and monitoring
- Integrated networking
- Cloud Console (view,inspect)

When you use GKE, you start by directing the service to instantiate a Kubernetes system for you. This system is called a ```cluster```. </br>
The virtual machines that host your containers inside of a GKE cluster are called ```nodes```.

> You might be aware that open source Kubernetes contains a dashboard, but it takes a lot of work to set it up securely. But the GCP Console is a dashboard for your GKE clusters and workloads they don't have to manage. It's more powerful than the Kubernetes dashboard.

### Compute Options Detail

<div align="center">
<img width="700" src="https://user-images.githubusercontent.com/59575502/194713701-ebe7351d-b044-40e5-906d-7f24bfab8ee9.png">
</div>

<img width="1000" src="https://user-images.githubusercontent.com/59575502/194714117-90255677-79f8-499e-a25d-c920fde16ed2.png">
<img width="1000" src="https://user-images.githubusercontent.com/59575502/194714124-8d5fd5dd-b2f7-4530-9c94-369e3bb739b0.png">
<img width="1000" src="https://user-images.githubusercontent.com/59575502/194714130-8c886fea-c3e2-4f3c-af56-ce08a02b49ae.png">
<img width="1000" src="https://user-images.githubusercontent.com/59575502/194714133-74fc5196-0d82-4d14-95f7-7e68c2072e36.png">
<img width="1000" src="https://user-images.githubusercontent.com/59575502/194714135-6e6a76bd-c257-4c5b-af48-6f04070b3a6d.png">
<img width="1000" src="https://user-images.githubusercontent.com/59575502/194714141-6ef85f84-2252-46d1-8d29-76114857b7a6.png">
  
  
### Kubernetes Concepts
To understand how Kubernetes works, there are two related concepts you need to understand.
- ```Kubernetes object model``` -> Each thing Kubernetes manages is represented by an object, and you can view and change these objects, attributes, and state.
- ```Declarative management``` -> Kubernetes expects you to tell it what you want the state of the objects under its management to be and it will work to bring that state into being and keep it there. How does it do that? By means of its so-called ```watch loop```.

#### Pods
- Pods are the ```basic building block``` of the standard Kubernetes module, and they are the ```smallest deployable Kubernetes object```.
- Every running **container** in a Kubernetes system is a Pod.
- A Pod embodies the environment **where containers live** and that environment can accommodate one or more containers. If there is more than one container in a Pod, they are tightly coupled and they share resources including networking and storage.
- Kubernetes assigns each Pod a **unique IP** address. Every container within a Pod shares the network namespace including IP address and network ports. Containers within the same Pod can communicate through localhost ```127.0.0.1```

### The Kubernetes Control Plane

<img width="1200" src="https://user-images.githubusercontent.com/59575502/194718806-aa1557e6-1703-4b8c-88c6-7c313eb124a7.png">

One computer is called the "control plane" and the others are simply called "nodes". 
- ```nodes``` - The job of the nodes is to run parts.
- ```control plane``` - The job of the control plane is to coordinate the entire cluster. 
- ```kube-apiserver``` - Its job is to accept commands that view or change the state of the cluster, including launching pods.
- ```etcd``` -  A database, Its job is to reliably store the state of the cluster.
- ```kube-scheduler``` - Responsible for scheduling pods onto nodes.
- ```kube-controller-manager``` - It continuously monitors the state of the cluster through kube-apiserver. Whenever the current state of the cluster doesn't match the desired state, kube-controller-manager will attempt to make changes to achieve the desired state. 

### Google Kubernetes Engine Concepts
- Kubernetes doesn't create nodes. ```Cluster admins``` create nodes and add them to Kubernetes.
- GKE manages this by deploying and registering ```Compute Engine instances as nodes```.

### A note about Services
- Services provide load-balanced access to specified Pods. There are three primary types of Services:
  - ```ClusterIP``` - Exposes the service on an IP address that is only accessible from within this cluster. This is the default type.
  - ```NodePort``` - Exposes the service on the IP address of each node in the cluster, at a specific port number.
  - ```LoadBalancer``` - Exposes the service externally, using a load balancing service provided by a cloud provider. 

In Google Kubernetes Engine, LoadBalancers give you access to a ```regional Network Load Balancing``` configuration by default. To get access to a global HTTP(S) Load Balancing configuration, you can use an ```Ingress``` object.

### Controller objects to know about
The relationship among several Kubernetes controller objects:
- ```ReplicaSets``` - ensures that a population of Pods, all identical to one another.
- ```Deployments``` - let you do declarative updates (create, update, roll back, and scale Pods) to ReplicaSets and Pods.
- ```Replication Controllers``` - similar role to the combination of ReplicaSets and Deployments (not recommended).
- ```StatefulSets``` - If you need to deploy applications that maintain local state
- ```DaemonSets``` - If you need to run certain Pods on all the nodes within the cluster or on a selection of nodes
- ```Jobs``` - creates one or more Pods required to run a task

