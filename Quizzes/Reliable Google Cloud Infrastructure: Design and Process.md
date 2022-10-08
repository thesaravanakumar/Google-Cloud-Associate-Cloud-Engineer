## Defining Services

- Which best describes an SLO?

  * [x] It is a target measure you want your service to achieve.
  * [ ] It is a contract with end users that guarantees service quality
  * [ ] It is a short, measurable description of an application feature.
  * [ ] It is a measurable, time bound key performance indicator for your application.

- Using SMART criteria, which below would be the least effective KPI?

  * [ ] Page views per hour
  * [x] User experience design
  * [ ] User sign ups per month
  * [ ] Clicks per session

- Which best describes a user story?

  * [ ] It is a short description of a typical person using the system.
  * [ ] It is a narrative that describes the sequence of steps a typical user would perform to accomplish some task or goal when using the system.
  * [x] It is a short description of a feature written from the user's point of view.
  * [ ] It is a requirement of the system you are developing.

## Microservice Design and Architecture

- You’re building a RESTful microservice. Which would be a valid data format for returning data to the client?

  * [ ] JSON
  * [ ] XML
  * [ ] HTML
  * [x] All of the above.

- You’re writing a service, and you need to handle a client sending you invalid data in the request. What should you return from the service?

  * [ ] A 200 error code
  * [ ] An XML exception
  * [x] A 400 error code
  * [ ] A 500 error code

- Which below would violate 12-factor app best practices?

  * [ ] Explicitly declare and isolate dependencies.
  * [ ] Keep development, testing, and production as similar as possible.
  * [x] Store configuration information in your source repository for easy versioning.
  * [ ] Treat logs as event streams and aggregate logs into a single source.

- You’ve re-architected a monolithic web application so state is not stored in memory on the web servers, but in a database instead. This has caused slow performance when retrieving user sessions though. What might be the best way to fix this?

  * [ ] Increase the number of CPUs in the database server.
  * [ ] Move session state back onto the web servers and use sticky sessions in the load balancer.
  * [ ] Make sure all web servers are in the same zone as the database.
  * [x] Use a caching service like Redis or Memorystore.

## DevOps Automation

- What Google Cloud feature would be easiest to use to automate a build in response to code being checked into your source code repository?  

  * [ ] App Engine  
  * [ ] Cloud Functions  
  * [x] Build triggers  
  * [ ] Cloud Scheduler  

- Which Google Cloud tools can be used to build a continuous integration pipeline?  

  * [ ] Cloud Source Repositories  
  * [ ] Cloud Build  
  * [ ] Container Registry  
  * [x] All of these  

## Choosing Storage Solutions

- Currently, you are using Firestore to store information about products, reviews, and user sessions. You'd like to speed up data access in a simple, cost-effective way. What would you recommend?

  * [x] Cache the data using Memorystore.
  * [ ] Move the data to BigQuery.
  * [ ] Move the data to Cloud Bigtable.
  * [ ] Move the data to Spanner.

- You want to analyze sales trends. To help achieve this, you want to combine data from your on-premises Oracle database with Google Analytics data and your web server logs. Where might you store the data so it is both easy to query and cost-effective?

  * [ ] Spanner
  * [x] BigQuery
  * [ ] Cloud SQL
  * [ ] Firestore


- You are a global financial services company with users all over the world. You need a database service that can provide low latency worldwide with strong consistency. Which service might you choose?

  * [ ] BigQuery
  * [x] Spanner
  * [ ] Cloud SQL
  * [ ] Firestore

- You need to store user preferences, product information, and reviews for a website you are building. There won't be a huge amount of data. What would be a simple, cost-effective, managed solution?

  * [ ] BigQuery
  * [ ] Cloud SQL
  * [ ] Spanner
  * [x] Firestore

## Google Cloud and Hybrid Network Architecture

- You want a secure, private connection between your network and a Google Cloud network. There is not a lot of volume, but the connection needs to be extremely reliable. Which configuration below would you choose? 

  * [ ] VPN
  * [x] VPN with high availability and Cloud Router.
  * [ ] Cloud Interconnect 
  * [ ] VPC peering 

- You have a contract with a service provider to manage your Google VPC networks. You want to connect a network they own to your VPC. Both networks are in Google Cloud. Which Connection option should you choose?

  * [ ] VPN with high availability and Cloud Router.
  * [ ] Cloud Interconnect
  * [ ] VPN 
  * [x] VPC peering

- You are a large bank deploying an online banking service to Google Cloud. The service needs high volume access to mainframe data on-premises. Which connectivity option would likely be best?

  * [x] Cloud Interconnect 
  * [ ] VPN 
  * [ ] Peering 
  * [ ] HTTPS 

- You are deploying a large-scale web application with users all over the world and a lot of static content. Which load balancer configuration would likely be the best?

  * [ ] HTTP load balancer with SSL configured.
  * [x] HTTP load balancer with SSL configured and the CDN enabled.
  * [ ] UDP load balancer with SSL configured and the CDN enabled.
  * [ ] TCP load balancer with SSL configured. 

## Deploying Applications to Google Cloud

- You've been asked to write a program that uses Vision API to check for inappropriate content in photos that are uploaded to a Cloud Storage bucket. Any photos that are inappropriate should be deleted. What might be the simplest, cheapest way to deploy in this program?

  * [x] Cloud Functions
  * [ ] Compute Engine
  * [ ] GKE
  * [ ] App Engine

- You have containerized multiple applications using Docker and have deployed them using Compute Engine VMs. You want to save on costs and simplify container management. What might you do?

  * [ ] Rewrite the applications to run in App Engine.
  * [ ] Rewrite the applications to run in Cloud Functions.
  * [x] Migrate the containers to GKE.
  * [ ] Write Terraform scripts for all deployment.

- You need to deploy an existing application that was written in .NET version 4. The application requires Windows servers, and you don't want to change it. Which should you use?

  * [x] Compute Engine
  * [ ] Cloud Functions
  * [ ] GKE
  * [ ] App Engine

## Designing Reliable Systems

- You're creating a service and you want to protect it from being overloaded by too many client retries in the event of a partial outage. Which design pattern would you implement?

  * [x] Circuit breaker
  * [ ] Overload feedback repudiation
  * [ ] Truncated exponential backoff
  * [ ] Lazy caching

- You need a relational database for a system that requires extremely high availability (99.999%). The system must run uninterrupted even in the event of a regional outage. Which database would you choose?

  * [ ] Firestore
  * [x] Spanner
  * [ ] BigQuery
  * [ ] Cloud SQL

## Security

- What do you have to do to enable encryption when using Cloud Storage?

  * [ ] Simply enable encryption when configuring a bucket.
  * [ ] Enable encryption and upload a key.
  * [ ] Create an encryption key using Cloud Key Management Service, and select it when creating a Cloud Storage bucket.
  * [x] Nothing as encryption is enabled by default.

- Which Google Cloud features could help reduce the risk of DDoS attacks?

  * [ ] HTTP global load balancer
  * [ ] CloudCDN
  * [ ] Google Cloud Armor
  * [x] All of these

- You don't want programmers to have access to production resources. What's the easiest way to do this in Google Cloud?

  * [ ] Create a firewall rule that blocks developer access to production servers and databases.
  * [ ] Set up private access and Identity-Aware Proxy.
  * [x] Create development and production projects, and don't give developers access to production.
  * [ ] Use different service accounts for production and development resources with your project.

- What Google Cloud service can you use to enforce the principle of least privilege when using Google Cloud?

  * [ ] Encryption keys
  * [ ] SSL certificates
  * [ ] Firewall rules
  * [x] IAM members and roles

## Maintenance and Monitoring

- Your service has an availability SLO of 99%. What could you use to monitor whether you are meeting it?

  * [ ] Readiness probe
  * [ ] Health check
  * [x] Uptime check
  * [ ] Liveness probe

- You're deploying test environments using Compute Engine VMs. Some downtime is acceptable, and it is very important to deploy them as inexpensively as possible. What single thing below could save you the most money?

  * [x] Preemptible machines
  * [ ] Sole tenant nodes
  * [ ] Sustained use discount
  * [ ] Committed use discount

- You made a minor update to a service and would like to test it in production by sending a small portion of requests to the new version. Which would you choose?

  * [ ] A/B testing
  * [ ] Rolling update
  * [x] Canary deployment
  * [ ] Blue/green deployment

- You've made a minor fix to one of your services. You want to deploy the new version with no downtime. Which would you choose?

  * [ ] Canary deployment
  * [x] Rolling update
  * [ ] A/B test
  * [ ] Blue/green deployment
