## Reliable Google Cloud Infrastructure: Design and Process

### Requirements, Analysis, and Design

<img width="900" src="https://user-images.githubusercontent.com/59575502/194763256-6c639c61-8694-4647-8b3e-a9c3ec519081.png">

### KPIs and SLIs
Key performance indicators (KPIs) are metrics that can be used to measure success
- In business, common KPIs include:
    - Return on investment (ROI)
    - Earnings before interest and taxes (EBIT)
    - Employee turnover
    - Customer churn
- In software, common KPls include:
    - Page views
    - User registrations
    - Clickthroughs
    - Checkouts

There are **four golden signals** that measure a system's performance and reliability.
- ```Latency``` -> measures how long it takes a particular part of a system to return a result.
- ```Traffic``` -> measures how many requests are reaching your system.
- ```Saturation``` -> measures how close to capacity a system is.
- ```Errors``` -> measure system failures or other issues.

Types of **targets** set for systems four golden signals metrics. 
- ```Service level indicators (SLI)``` -> carefully selected monitoring metrics that measure one aspect of a services reliability.
- ```Service level objective (SLO)``` -> combines a service level indicator with a target reliability. 
- ```Service-level agreements (SLA)``` -> commitments made to your customers that your systems and applications will only have a certain amount of downtime.

![image](https://user-images.githubusercontent.com/59575502/194767132-bb2e3a1a-f7c5-4b9e-959c-55b3ee1331bf.png)

#### Stateful vs Stateless services

Stateful services have different challenges than stateless ones 
- Stateful services manage stored data over time
  - Harder to scale
  - Harder to upgrade
  - Need to back up
- Stateless services get their data from the environment or other stateful services 
  - Easy to scale by adding instances 
  - Easy to migrate to new versions 
  - Easy to administer

### The Twelve-Factor App

The Twelve-Factor App is a set of best practices for building web or software-as-a-service applications
- Maximize portability 
- Deploy to the cloud 
- Enable continuous deployment 
- Scale easily

![image](https://user-images.githubusercontent.com/59575502/194767809-b9226e9d-3068-4ca7-bd3a-efb03b15a9bd.png)

<div align="center">
<img width="600" src="https://user-images.githubusercontent.com/59575502/194767817-c76927fc-94f9-4a6c-afe1-ad331a2f35ba.png">
</div>

### REST

REST architecture supports loose coupling
- REST stands for Representational State Transfer
- Protocol independent
    - HTTP is most common 
    - Others possible like gRPC
- Service endpoints supporting REST are called RESTful
- Client and Server communicate with Request - Response processing

### HTTP
Clients access services using HTTP requests
- ```VERB``` - GET, PUT, POST, DELETE
- ```URI``` - Uniform Resource Identifier (endpoint)
- ```Request Header``` - metadata about the message
    - Preferred representation formats (e.g., JSON, XML)
- Request Body: (Optional) Request state
    - Representation (JSON, XML) of resource

```
GET / HTTP/1.1 
Host: pets.drehnstrom.com
POST /add HTTP/1.1
```
```
Host: pets.drehnstrom.com 
Content-Type: json 
Content-Length: 35

{"name" : "Noir", "breed":"Schnoodle"}
```

The HTTP verb tells the server what to do
- ```GET``` is used to retrieve data 
- ```POST``` is used to create data
  - Generates entity ID and returns it to the client
- PUT is used to create data or alter existing data
  - Entity ID must be known 
  - PUT should be idempotent, which means that whether the request is made once or multiple times, the effects on the data are exactly the same
- DELETE is used to remove data

#### Services return HTTP responses
- Response Code: 3-digit HTTP status code
  - 200 codes for success
  - 400 codes for client errors
  - 500 codes for server errors 
- Response Body: contains resource representation 
  - JSON, XML, HTML, etc.

### APIs
It's important to design consistent APls for services
- Each Google Cloud service exposes a REST API 
  - Functions are in the form: ```service.collection.verb```
  - Parameters are passed either in the URL or in the request body in JSON format 
- For example, the Compute Engine API has...
  - A service endpoint at: https://compute.googleapis.com 
  - Collections include instances, instanceGroups, instance Templates, etc.
  - Verbs include insert, list, get, etc. 
-  So, to see all your instances, make a GET request to:
https://compute.googleapis.com/compute/v1/projects/{project}/zones/{zone}/instances

### OpenAPI
OpenAPI is an industry-standard for exposing APIs to clients
- Standard interface description format for REST APIs 
  - Language independent
  - Open-source (based on Swagger) 
- Allows tools and humans to understand how to use a service without needing its source code

> gRPC - Internal microservice communications.

<img width="1200" src="https://user-images.githubusercontent.com/59575502/194769402-5b0f3214-01bc-4bb7-9b4c-82287c4388fc.png">

```Cloud Endpoints``` is an API management gateway which helps you develop, deploy, and manage APIs on any Google Cloud backend. </br>
```Apigee``` is an API management platform built for enterprises, with deployment options on cloud, on-premises, or hybrid. The feature set includes an API gateway, customizable portal for onboarding partners and developers, monetization, and deep analytics around APIs. You can use Apigee for any HTTP/ HTTPS backends

### Continuous Integration Pipelines

<div align="center">
<img width="700" src="https://user-images.githubusercontent.com/59575502/194769657-56e18feb-405f-46b9-9f0c-603991393444.png">
</div>

#### For cloud storage click [here](https://github.com/thesaravanakumar/Google-Cloud-Associate-Cloud-Engineer/blob/main/Notes/Essential%20Google%20Cloud%20Infrastructure:%20Core%20Services.md#storage).

### Designing Google Cloud Load Balancers

![image (1)](https://user-images.githubusercontent.com/59575502/194770172-0497dc75-4261-4d90-a712-5e3d8b284144.png)

<div align="center">
<img width="800" src="https://user-images.githubusercontent.com/59575502/194770176-ae178b92-c541-4e0c-8994-ca01b3e98d12.png">
<img width="800" src="https://user-images.githubusercontent.com/59575502/194770494-d220c4b3-2f4b-43f6-a630-75ce252a0675.png">  
</div>

### Key Performance Metrics and Reliability

![image](https://user-images.githubusercontent.com/59575502/194771074-0a96a1dc-f5cd-4105-891f-1e66e7ff5743.png)
![image (1)](https://user-images.githubusercontent.com/59575502/194771076-90ac0487-4252-403b-a8ba-5418858d537b.png)
![image (2)](https://user-images.githubusercontent.com/59575502/194771080-3359f819-d54b-40bc-b1eb-2b4646c64669.png)

<div align="center">
<img width="800" src="https://user-images.githubusercontent.com/59575502/194771082-ef7df977-a6ea-456b-8e64-03440bb385f1.png">  
</div>

</br> 

> For VPC Networking, network connectivity products (peering, Cloud VPN, and Cloud Interconnect) and other topics check my notes in other files.
