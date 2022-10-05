## Diagnostic questions

- Stella is a new member of a team in your company who has been put in charge of monitoring VM instances in the organization. Stella will need the required permissions to perform this role. How should you grant her those permissions?

  * [ ] Assign Stella a roles/compute.viewer role.
  * [ ] Assign Stella compute.instances.get permissions on all of the projects she needs to monitor.
  * [x] Add Stella to a Google Group in your organization. Bind that group to roles/compute.viewer.
  * [ ] Assign the “viewer” policy to Stella. 

- How are resource hierarchies organized in Google Cloud?

  * [ ] Organization, Project, Resource, Folder
  * [x] Organization, Folder, Project, Resource
  * [ ] Project, Organization, Folder, Resource 
  * [ ] Resource, Folder, Organization, Project

- What Google Cloud project attributes can be changed?

  * [ ] The Project ID.
  * [x] The Project Name.
  * [ ] The Project Number.
  * [ ] The Project Category.

- Jane will manage objects in Cloud Storage for the Cymbal Superstore. She needs to have access to the proper permissions for every project across the organization. What should you do? 

  * [ ] Assign Jane theroles/storage.objectCreatoron every project.
  * [ ] Assign Jane the roles/vieweron each project and theroles/storage.objectCreatorfor each bucket.
  * [ ] Assign Jane the roles/editor at the organizational level.
  * [x] Add Jane to a group that has the roles/storage.objectAdmin role assigned at the organizational level. 

- You need to add new groups of employees in Cymbal Superstore’s production environment. You need to consider Google’s recommendation of using least privilege. What should you do? 

  * [ ] Grant the most restrictive basic role to most services, grant predefined or custom roles as necessary.
  * [x] Grant predefined and custom roles that provide necessary permissions and grant basic roles only where needed.
  * [ ] Grant the least restrictive basic roles to most services and grant predefined and custom roles only when necessary.
  * [ ] Grant custom roles to individual users and implement basic roles at the resource level. 

- The Operations Department at Cymbal Superstore wants to provide managers access to information about VM usage without allowing them to make changes that would affect the state. You assign them the Compute Engine Viewer role. Which TWO permissions will they receive?

  * [ ] computer.images.update
  * [ ] compute.images.setIAM
  * [x] compute.images.get
  * [x] compute.images.list
  * [ ] compute.images.create

- How are billing accounts applied to projects in Google Cloud? (Choose TWO).

  * [ ] If your project only uses free resources you don’t need a link to an active billing account. 
  * [x] A billing account can be linked to one or more projects.
  * [ ] A project and its resources can be tied to more than one billing account.
  * [x] A project and its resources can only be tied to one billing account.
  * [ ] Set up Cloud Billing to pay for usage costs in Google Cloud projects and Google Workspace accounts.

- Fiona is the billing administrator for the project associated with Cymbal Superstore’s eCommerce application. Jeffrey, the marketing department lead, wants to receive emails related to budget alerts. Jeffrey should have access to no additional billing information. What should you do?
  * [ ] Change the budget alert default threshold rules to include Jeffrey as a recipient.
  * [x] Use Cloud Monitoring notification channels to send Jeffrey an email alert. 
  * [ ] Add Jeffrey and Fiona to the budget scope custom email delivery dialog.
  * [ ] Send alerts to a Pub/Sub topic that Jeffrey is subscribed to.

- Pick TWO choices, from the options below, that provide a command line interface to Google Cloud.

  * [ ] Google Cloud console
  * [x] Cloud Shell
  * [ ] Cloud Console Mobile App
  * [x] Cloud SDK
  * [ ] REST-based API

- You want to use the Cloud Shell to copy files to your Cloud Storage bucket. Which Cloud SDK command should you use?

  * [ ] gcloud
  * [x] gsutil
  * [ ] bq
  * [ ] Cloud Storage Browser

---

- Which Google Cloud interface allows for scripting actions in a set of command line executables?

  * [ ] Google Cloud console
  * [x] Cloud Shell
  * [ ] Cloud Mobile App
  * [ ] REST API

- What is the lowest level basic role that gives you permissions to change resource state?

  * [ ] Owner.
  * [ ] Administrator.
  * [ ] Viewer.
  * [x] Editor. 

---

- The projected amount of cloud storage required for Cymbal Superstore to enable users to post pictures for project reviews is 10 TB of immediate access storage in the US and 30 TB of storage for historical posts in a bucket located near Cymbal Superstore’s headquarters. The contents of this bucket will need to be accessed once every 30 days. You want to estimate the cost of these storage resources to ensure this is economically feasible. What should you do?

  * [ ] Use the pricing calculator to estimate the costs for 10 TB of regional standard storage, 30 TB of regional Coldline storage, and egress charges for reads from storage.
  * [ ] Use the pricing calculator to estimate the price for 10 TB of regional standard storage, 30 TB of regional Nearline storage, and ingress charges for posts to the bucket.
  * [ ] Use the pricing calculator to estimate the price for 10 TB of multi-region standard storage, 30 TB for regional Coldline storage, and ingress charges for posts to the bucket.
  * [x] Use the pricing calculator to estimate the price for 10 TB of multi-region standard storage, 30 TB for regional Nearline, and egress charges for reads from the bucket.

- Cymbal Superstore decides to migrate their supply chain application to Google Cloud. You need to configure specific operating system dependencies. What should you do?

  * [ ] Implement an application using containers on Cloud Run.
  * [ ] Implement an application using code on App Engine.
  * [ ] Implement an application using containers on Google Kubernetes Engine.
  * [x] Implement an application using virtual machines on Compute Engine.

- Cymbal Superstore decides to pilot a cloud application for their point of sale system in their flagship store. You want to focus on code and develop your solution quickly, and you want your code to be portable. How do you proceed?

  * [ ] SSH into a Compute Engine VM and execute your code.
  * [x] Package your code to a container image and post it to Cloud Run.
  * [ ] Implement a deployment manifest and run kubectl apply on it in Google Kubernetes Engine.
  * [ ] Code your solution in Cloud Functions.

- An application running on a highly-customized version of Ubuntu needs to be migrated to Google Cloud. You need to do this in the least amount of time with minimal code changes. How should you proceed?

  * [x] Create Compute Engine Virtual Machines and migrate the app to that infrastructure
  * [ ] Deploy the existing application to App Engine.
  * [ ] Deploy your application in a container image to Cloud Run. 
  * [ ] Implement a Kubernetes cluster and create pods to enable your app.

- You want to deploy a microservices application. You need full control of how you manage containers, reliability, and autoscaling, but don’t want or need to manage the control plane. Which compute option should you use?

  * [ ] Cloud Run
  * [ ] App Engine
  * [x] Google Kubernetes Engine
  * [ ] Compute Engine

- Cymbal Superstore needs to analyze whether they met quarterly sales projections. Analysts assigned to run this query are familiar with SQL. What data solution should they implement?

  * [x] BigQuery
  * [ ] Cloud SQL
  * [ ] Cloud Spanner
  * [ ] Cloud Firestore

- Cymbal Superstore’s supply chain application frequently analyzes large amounts of data to inform business processes and operational dashboards. What storage class would make sense for this use case?

  * [ ] Multi-regional
  * [x] Regional
  * [ ] Nearline
  * [ ] Coldline

- Cymbal Superstore has a need to populate visual dashboards with historical time-based data. This is an analytical use-case. Which TWO storage solutions could they use? 

  * [x] BigQuery
  * [ ] Cloud Storage
  * [ ] Cloud Firestore
  * [ ] Cloud SQL
  * [x] Cloud Bigtable 

- Cymbal Superstore is piloting an update to its ecommerce app for the flagship store in Minneapolis, Minnesota. The app is implemented as a three-tier web service with traffic originating from the local area and resources dedicated for it in us-central1. You need to configure a secure, low-cost network load-balancing architecture for it. How do you proceed?

  * [ ] Implement a premium tier pass-through external https load balancer connected to the web tier as the frontend and a regional internal load balancer between the web tier and backend.
  * [ ] Implement a proxied external TCP/UDP network load balancer connected to the web tier as the frontend and a premium network tier ssl load balancer between the web tier and the backend. 
  * [x] Configure a standard tier proxied external https load balancer connected to the web tier as a frontend and a regional internal load balancer between the web tier and the backend. 
  * [ ] Configure a proxied SSL load balancer connected to the web tier as the frontend and a standard tier internal TCP/UDP load balancer between the web tier and the backend. 

- Which Google Cloud load balancing option runs at Layer 7 of the TCP stack?

  * [x] Global http(s)
  * [ ] Global SSL Proxy
  * [ ] Global TCP Proxy
  * [ ] Regional Network

---

- Which storage class is designed for long term storage has a 365 day minimum storage agreement, and a lower storage price as compared to other storage types?

  * [ ] Standard storage
  * [ ] Cold Line storage
  * [ ] Nearline storage
  * [x] Archive storage

- Which serverless option is based on developing and executing small snippets of code?

  * [x] Cloud Functions
  * [ ] Cloud Run
  * [ ] BigQuery
  * [ ] Dataflow

---

- Cymbal Superstore’s sales department has a medium-sized MySQL database. This database includes user-defined functions and is used internally by the marketing department at Cymbal Superstore HQ. The sales department asks you to migrate the database to Google Cloud in the most timely and economical way. What should you do? 

  * [ ] Find a MySQL machine image in Cloud Marketplace and configure it to meet your needs.
  * [ ] Implement a database instance using Cloud SQL, back up your local data, and restore it to the new instance.
  * [x] Configure a Compute Engine VM with an N2 machine type, install MySQL, and restore your data to the new instance. 
  * [ ] Use gcloud to implement a Compute Engine instance with an E2-standard-8 machine type, install, and configure MySQL.

- The backend of Cymbal Superstore’s e-commerce system consists of managed instance groups. You need to update the operating system of the instances in an automated way using minimal resources. What do you do?

  * [ ] Create a new instance template. Click Update VMs. Set the update type to Opportunistic. Click Start.
  * [x] Create a new instance template, then click Update VMs. Set the update type to PROACTIVE. Click Start. 
  * [ ] Create a new instance template. Click Update VMs. Set max surge to 5. Click Start.
  * [ ] Abandon each of the instances in the managed instance group. Delete the instance template, replace it with a new one, and recreate the instances in the managed group. 

- The development team for the supply chain project is ready to start building their new cloud app using a small Kubernetes cluster for the pilot. The cluster should only be available to team members and does not need to be highly available. The developers also need the ability to change the cluster architecture as they deploy new capabilities. How would you implement this?

  * [ ] Implement an autopilot cluster in us-central1-a with a default pool and an Ubuntu image.
  * [x] Implement a private standard zonal cluster in us-central1-a with a default pool and an Ubuntu image.
  * [ ] Implement a private standard regional cluster in us-central1 with a default pool and container-optimized image type. 
  * [ ] Implement an autopilot cluster in us-central1 with an Ubuntu image type.

- You need to quickly deploy a containerized web application on Google Cloud. You know the services you want to be exposed. You do not want to manage infrastructure. You only want to pay when requests are being handled and need support for custom packages. What technology meets these needs?

  * [ ] App Engine Flexible
  * [ ] App Engine Standard
  * [x] Cloud Run
  * [ ] Cloud Functions

You need to analyze and act on files being added to a Cloud Storage bucket. Your programming team is proficient in Python. The analysis you need to do takes at most 5 minutes. You implement a Cloud Function to accomplish your processing and specify a trigger resource pointing to your bucket. How should you configure the --trigger-event parameter using gcloud?

  * [x] --trigger-event google.storage.object.finalize
  * [ ] --trigger-event google.storage.object.create
  * [ ] --trigger-event google.storage.object.change
  * [ ] --trigger-event google.storage.object.add

- You require a Cloud Storage bucket serving users in New York City. There is a need for geo-redundancy. You do not plan on using ACLs. What CLI command do you use?

  * [ ] Run a gcloud mb command specifying the name of the bucket and accepting defaults for the other mb settings.
  * [ ] Run a gsutil mb command specifying a multi-regional location and an option to turn ACL evaluation off. 
  * [x] Run a gsutil mb command specifying a dual-region bucket and an option to turn ACL evaluation off. 
  * [ ] Run a gsutil mb command specifying a dual-region bucket and accepting defaults for the other mb settings.

- Cymbal Superstore asks you to implement Cloud SQL as a database backend to their supply chain application. You want to configure automatic failover in case of a zone outage. You decide to use thegcloud sql instances create command set to accomplish this. Which gcloud command line argument is required to configure the stated failover capability as you create the required instances?

  * [x] --availability-type
  * [ ] --replica-type
  * [ ] --secondary-zone
  * [ ] --master-instance-name

- Cymbal Superstore’s marketing department needs to load some slowly changing data into BigQuery. The data arrives hourly in a Cloud Storage bucket. You want to minimize cost and implement this in the fewest steps. What should you do?

  * [ ] Implement a bq load command in a command line script and schedule it with cron. 
  * [ ] Read the data from your bucket by using the BigQuery streaming API in a program. 
  * [ ] Create a Cloud Function to push data to BigQuery through a Dataflow pipeline.
  * [x] Use the BigQuery data transfer service to schedule a transfer between your bucket and BigQuery.

- Which Virtual Private Cloud (VPC) network type allows you to fully control IP ranges and the definition of regional subnets?

  * [ ] Default Project network
  * [ ] Auto mode network
  * [x] Custom mode network 
  * [ ] An auto mode network converted to a custom network 

- What action does theterraform apply command perform?

  * [ ] Downloads the latest version of the terraform provider.
  * [ ] Verifies syntax of terraform config file.
  * [ ] Shows a preview of resources that will be created.
  * [x] Sets up resources requested in the terraform config file.

---

- Which data storage service is a unique globally available, horizontally scalable database with relational semantics?

  * [ ] BigQuery
  * [ ] Cloud SQL
  * [x] Cloud Spanner
  * [ ] Bigtable

- Which services are based on logic implemented in containers? (Pick two).

  * [ ] Cloud Functions
  * [x] Cloud Run
  * [x] Google Kubernetes Engine
  * [ ] Compute Engine
  * [ ] Managed Instance Groups

---

- You want to view a description of your available snapshots using the command line interface (CLI). What gcloud command should you use?

  * [x] gcloud compute snapshots list
  * [ ] gcloud snapshots list
  * [ ] gcloud compute snapshots get
  * [ ] gcloud compute list snapshots

- You have a scheduled snapshot you are trying to delete, but the operation returns an error. What should you do to resolve this problem?

  * [ ] Delete the downstream incremental snapshots before deleting the main reference.
  * [ ] Delete the object the snapshot was created from.
  * [x] Detach the snapshot schedule before deleting it.
  * [ ] Restore the snapshot to a persistent disk before deleting it.

- Which of the following tasks are part of the process when configuring a managed instance group? (Pick two).

  * [x] Defining Health checks
  * [x] Providing Number of instances
  * [ ] Specifying Persistent disks
  * [ ] Choosing instance Machine type
  * [ ] Configuring the operating system

- Cymbal Superstore’s GKE cluster requires an internal http(s) load balancer. You are creating the configuration files required for this resource. What is the proper setting for this scenario? 

  * [ ] Annotate your ingress object with an ingress.class of “gce.”
  * [ ] Configure your service object with a type: LoadBalancer.
  * [x] Annotate your service object with a neg reference.
  * [ ] Implement custom static routes in your VPC:

- What Kubernetes object provides access to logic running in your cluster via endpoints that you define?

  * [ ] Pod templates
  * [ ] Pods
  * [x] Services
  * [ ] Deployments

- What is the declarative way to initialize and update Kubernetes objects?

  * [x] kubectl apply
  * [ ] kubectl create
  * [ ] kubectl replace
  * [ ] kubectl run

- You have a Cloud Run service with a database backend. You want to limit the number of connections to your database. What should you do?

  * [ ] Set Min instances.
  * [x] Set Max instances.
  * [ ] Set CPU Utilization.
  * [ ] Set Concurrency settings.

- You want to implement a lifecycle rule that changes your storage type from standard to nearline after a specific date. What conditions should you use? (Pick two).

  * [ ] Age
  * [x] CreatedBefore
  * [x] MatchesStorageClass
  * [ ] IsLive
  * [ ] NumberofNewerVersions

- Cymbal Superstore has a subnetwork called mysubnet with an IP range of 10.1.2.0/24. You need to expand this subnet to include enough IP addresses for at most 2000 new users or devices. What should you do?

  * [ ] gcloud compute networks subnets expand-ip-range mysubnet --region us-central1 --prefix-length 20
  * [ ] gcloud networks subnets expand-ip-range mysubnet --region us-central1 --prefix-length 21
  * [x] gcloud compute networks subnets expand-ip-range mysubnet --region us-central1 --prefix-length 21
  * [ ] gcloud compute networks subnets expand-ip-range mysubnet --region us-cetnral1 --prefix-length 22

- Cymbal Superstore’s supply chain management system has been deployed and is working well. You are tasked with monitoring the system’s resources so you can react quickly to any problems. You want to ensure the CPU usage of each of your Compute Engine instances in us-central1 remains below 60%. You want an incident created if it exceeds this value for 5 minutes. You need to configure the proper alerting policy for this scenario. What should you do?

  * [ ] Choose resource type of VM instance and metric of CPU load, condition trigger if any time series violates, condition is below, threshold is .60, for 5 minutes.
  * [ ] Choose resource type of VM instance and metric of CPU utilization, condition trigger all time series violates, condition is above, threshold is .60 for 5 minutes.
  * [ ] Choose resource type of VM instance, and metric of CPU utilization, condition trigger if any time series violates, condition is below, threshold is .60 for 5 minutes.
  * [x] Choose resource type of VM instance and metric of CPU utilization, condition trigger if any time series violates, condition is above, threshold is .60 for 5 minutes.

---

- What GKE object implements an http(s) load balancer?

  * [ ] Service
  * [ ] Pod
  * [ ] Deployment
  * [x] Ingress

- Which Cloud Run autoscaling setting should you set if you want to limit cost?

  * [ ] Min instances
  * [x] Max instances
  * [ ] Concurrency settings
  * [ ] CPU Utilization

---

- You need to configure access to Cloud Spanner from the GKE cluster that is supporting Cymbal Superstore’s ecommerce microservices application. You want to specify an account type to set the proper permissions. What should you do?

  * [ ] Assign permissions to a Google account referenced by the application
  * [ ] Assign permissions through a Google Workspace account referenced by the application
  * [ ] Assign permissions through service account referenced by the application
  * [x] Assign permissions through a Cloud Identity account referenced by the application

- You are trying to assign roles to the dev and prod projects of Cymbal Superstore’s e-commerce app but are receiving an error when you try to run set-iam policy. The projects are organized into an ecommerce folder in the Cymbal Superstore organizational hierarchy. You want to follow best practices for the permissions you need while respecting the practice of least privilege. What should you do?

  * [ ] Ask your administrator for resourcemanager.projects.setIamPolicy roles for each project
  * [x] Ask your administrator for the roles/resourcemanager.folderIamAdmin for the ecommerce folder
  * [ ] Ask your administrator for the roles/resourcemanager.organizationAdmin for Cymbal Superstore 
  * [ ] Ask your administrator for the roles/iam.securityAdmin role in IAM.

- You have a custom role implemented for administration of the dev/test environment for Cymbal Superstore’s transportation management application. You are developing a pilot to use Cloud Run instead of Cloud Functions. You want to ensure your administrators have the correct access to the new resources. What should you do?

  * [x] Make the change to the custom role locally and run an update on the custom role
  * [ ] Delete the custom role and recreate a new custom role with required permissions
  * [ ] Copy the existing role, add the new permissions to the copy, and delete the old role
  * [ ] Create a new role with needed permissions and migrate users to it.

- Which of the scenarios below is an example of a situation where you should use a service account?

  * [ ] To directly access user data
  * [ ] For development environments
  * [ ] For interactive analysis
  * [x] For individual GKE pods

- Cymbal Superstore is implementing a mobile app for end users to track deliveries that are en route to them. The app needs to access data about truck location from Pub/Sub using Google recommended practices. What kind of credentials should you use?

  * [ ] API key
  * [ ] OAuth 2.0 client
  * [ ] Environment provided service account
  * [x] Service account key

- Which Cloud Audit log is disabled by default with a few exceptions?

  * [ ] Admin Activity audit logs
  * [x] Data Access audit logs
  * [ ] System Event audit logs
  * [ ] Policy Denied audit logs

- Outline where Cloud Audit logs can be accessed: in the logging tab of the operations interface. You are configuring audit logging for Cloud Storage. You want to know when objects are added to a bucket. Which type of audit log entry should you monitor?

  * [ ] Admin Activity log entries
  * [ ] ADMIN_READ log entries
  * [ ] DATA_READ log entries
  * [x] DATA_WRITE log entries

---

- What kind of account is meant for machine-to-machine communication in Google Cloud?

  * [ ] User account
  * [ ] Google Workspace account
  * [x] Service account
  * [ ] Cloud Identity account

- You are authenticating an application to service APIs. Both resources are internal to the Google Cloud environment. What type of credentials should you use?

  * [ ] User account credentials
  * [ ] Locally stored keys
  * [ ] API keys
  * [x] Temporary credentials
