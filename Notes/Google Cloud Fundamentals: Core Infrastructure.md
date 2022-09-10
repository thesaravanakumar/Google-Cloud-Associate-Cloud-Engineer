## Google Cloud Fundamentals: Core Infrastructure

**Goal:** To provide an overview of Google Cloud

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


The US National Institute of Standards and Technology created the term **"cloud computing"** 
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
- ***I***nfrastructure ***a***s ***a*** ***S***ervice ( Compute, Storage, Networks )
  - Organized virtually into resources that are similar to physical data centers.
  - Pay for what they allocate.
- ***P***latform ***a***s ***a*** ***S***ervice
  - Cloud environment that has everything developers need to build, run, and manage applications. No need to maintain software development platform.
  - Pay for what they use.
- ***S***oftware ***a***s ***a*** ***S***ervice ( Gmail, Docs )
  - Not installed in local system.
  - They run in cloud as a service ( can consume directly )

### **Regions:** 

Google Cloud’s infrastructure is based in five major geographic locations: **North America, South America, Europe, Asia, and Australia.**
**Example Region:** europe-west2 </br>
**Zones:** europe-west2-a, europe-west2-b, europe-west2-c </br>
check current location [here](https://cloud.google.com/about/locations).
<p align="center">
<img align="center" src="https://user-images.githubusercontent.com/59575502/189482754-b8f6715e-8f9e-443d-bcfb-e916ffcc08d9.png">
</p>


