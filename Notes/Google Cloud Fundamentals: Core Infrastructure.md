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
#### Virtual Private Cloud:
A Virtual Private Clouds or VPC is a secure individual private cloud computing model hosted within a public cloud, like Google Cloud. 
- Customers can run code, store data, host websites and do anything else they could do in an ordinary private cloud.
- This private cloud is hosted remotely by a public cloud provider.
