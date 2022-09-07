### **Section 1. Setting up a cloud solution environment**

1.1 Setting up cloud projects and accounts. Activities include:

    a. Creating a resource hierarchy

    b. Applying organizational policies to the resource hierarchy

    c. Granting members IAM roles within a project

    d. Managing users and groups in Cloud Identity (manually and automated)

    e. Enabling APIs within projects

    f. Provisioning and setting up products in Google Cloud’s operations suite

1.2 Managing billing configuration. Activities include:

    a. Creating one or more billing accounts

    b. Linking projects to a billing account

    c. Establishing billing budgets and alerts

    d. Setting up billing exports

1.3 Installing and configuring the command line interface (CLI), specifically the Cloud SDK (e.g., setting the default project).

</br>

### **Section 2. Planning and configuring a cloud solution**

2.1 Planning and estimating Google Cloud product use using the Pricing Calculator

2.2 Planning and configuring compute resources. Considerations include:

    a. Selecting appropriate compute choices for a given workload (e.g., Compute Engine, Google Kubernetes Engine, Cloud Run, Cloud Functions)

    b. Using preemptible VMs and custom machine types as appropriate

2.3 Planning and configuring data storage options. Considerations include:

    a. Product choice (e.g., Cloud SQL, BigQuery, Firestore, Cloud Spanner, Cloud Bigtable)

    b. Choosing storage options (e.g., Zonal persistent disk, Regional balanced persistent disk, Standard, Nearline, Coldline, Archive)

2.4 Planning and configuring network resources. Tasks include:

    a. Differentiating load balancing options

    b. Identifying resource locations in a network for availability

    c. Configuring Cloud DNS

</br>

### **Section 3. Deploying and implementing a cloud solution**

3.1 Deploying and implementing Compute Engine resources. Tasks include:

    a. Launching a compute instance using the Google Cloud console and Cloud SDK (gcloud) (e.g., assign disks, availability policy, SSH keys)

    b. Creating an autoscaled managed instance group using an instance template

    c. Generating/uploading a custom SSH key for instances

    d. Installing and configuring the Cloud Monitoring and Logging Agent

    e. Assessing compute quotas and requesting increases

3.2 Deploying and implementing Google Kubernetes Engine resources. Tasks include:

    a. Installing and configuring the command line interface (CLI) for Kubernetes (kubectl)

    b. Deploying a Google Kubernetes Engine cluster with different configurations including AutoPilot, regional clusters, private clusters, etc.

    c. Deploying a containerized application to Google Kubernetes Engine

    d. Configuring Google Kubernetes Engine monitoring and logging

3.3 Deploying and implementing Cloud Run and Cloud Functions resources. Tasks include, where applicable:

    a. Deploying an application and updating scaling configuration, versions, and traffic splitting

    b. Deploying an application that receives Google Cloud events (e.g., Pub/Sub events, Cloud Storage object change notification events)

3.4 Deploying and implementing data solutions. Tasks include:

    a. Initializing data systems with products (e.g., Cloud SQL, Firestore, BigQuery, Cloud Spanner, Pub/Sub, Cloud Bigtable, Dataproc, Dataflow, Cloud Storage)

    b. Loading data (e.g., command line upload, API transfer, import/export, load data from Cloud Storage, streaming data to Pub/Sub)

3.5 Deploying and implementing networking resources. Tasks include:

    a. Creating a VPC with subnets (e.g., custom-mode VPC, shared VPC)

    b. Launching a Compute Engine instance with custom network configuration (e.g., internal-only IP address, Google private access, static external and private IP address, network tags)

    c. Creating ingress and egress firewall rules for a VPC (e.g., IP subnets, network tags, service accounts)

    d. Creating a VPN between a Google VPC and an external network using Cloud VPN

    e. Creating a load balancer to distribute application network traffic to an application (e.g., Global HTTP(S) load balancer, Global SSL Proxy load balancer, Global TCP Proxy load balancer, regional network load balancer, regional internal load balancer)

3.6 Deploying a solution using Cloud Marketplace. Tasks include:

    a. Browsing the Cloud Marketplace catalog and viewing solution details

    b. Deploying a Cloud Marketplace solution

3.7 Implementing resources via infrastructure as code. Tasks include:

    a. Building infrastructure via Cloud Foundation Toolkit templates and implementing best practices

    b. Installing and configuring Config Connector in Google Kubernetes Engine to create, update, delete, and secure resources

</br>

### **Section 4. Ensuring successful operation of a cloud solution**

4.1 Managing Compute Engine resources. Tasks include:

    a. Managing a single VM instance (e.g., start, stop, edit configuration, or delete an instance)

    b. Remotely connecting to the instance

    c. Attaching a GPU to a new instance and installing necessary dependencies

    d. Viewing current running VM inventory (instance IDs, details)

    e. Working with snapshots (e.g., create a snapshot from a VM, view snapshots, delete a snapshot)

    f. Working with images (e.g., create an image from a VM or a snapshot, view images, delete an image)

    g. Working with instance groups (e.g., set autoscaling parameters, assign instance template, create an instance template, remove instance group)

    h. Working with management interfaces (e.g., Google Cloud console, Cloud Shell, Cloud SDK)

4.2 Managing Google Kubernetes Engine resources. Tasks include:

    a. Viewing current running cluster inventory (nodes, pods, services)

    b. Browsing Docker images and viewing their details in the Artifact Registry

    c. Working with node pools (e.g., add, edit, or remove a node pool)

    d. Working with pods (e.g., add, edit, or remove pods)

    e. Working with services (e.g., add, edit, or remove a service)

    f. Working with stateful applications (e.g. persistent volumes, stateful sets)

    g. Managing Horizontal and Vertical autoscaling configurations

    h. Working with management interfaces (e.g., Google Cloud console, Cloud Shell, Cloud SDK, kubectl)

4.3 Managing Cloud Run resources. Tasks include:

    a. Adjusting application traffic-splitting parameters

    b. Setting scaling parameters for autoscaling instances

    c. Determining whether to run Cloud Run (fully managed) or Cloud Run for Anthos

4.4 Managing storage and database solutions. Tasks include:

    a. Managing and securing objects in and between Cloud Storage buckets

    b. Setting object life cycle management policies for Cloud Storage buckets

    c. Executing queries to retrieve data from data instances (e.g., Cloud SQL, BigQuery, Cloud Spanner, Datastore, Cloud Bigtable)

    d. Estimating costs of data storage resources

    e. Backing up and restoring database instances (e.g., Cloud SQL, Datastore)

    f. Reviewing job status in Dataproc, Dataflow, or BigQuery

4.5 Managing networking resources. Tasks include:

    a. Adding a subnet to an existing VPC

    b. Expanding a subnet to have more IP addresses

    c. Reserving static external or internal IP addresses

    d. Working with CloudDNS, CloudNAT, Load Balancers and firewall rules

4.6 Monitoring and logging. Tasks include:

    a. Creating Cloud Monitoring alerts based on resource metrics

    b. Creating and ingesting Cloud Monitoring custom metrics (e.g., from applications or logs)

    c. Configuring log sinks to export logs to external systems (e.g., on-premises or BigQuery)

    d. Configuring log routers

    e. Viewing and filtering logs in Cloud Logging

    f. Viewing specific log message details in Cloud Logging

    g. Using cloud diagnostics to research an application issue (e.g., viewing Cloud Trace data, using Cloud Debug to view an application point-in-time)

    h. Viewing Google Cloud status

</br>

### **Section 5. Configuring access and security**

5.1 Managing Identity and Access Management (IAM). Tasks include:

    a. Viewing IAM policies

    b. Creating IAM policies

    c. Managing the various role types and defining custom IAM roles (e.g., primitive, predefined and custom)

5.2 Managing service accounts. Tasks include:

    a. Creating service accounts

    b. Using service accounts in IAM policies with minimum permissions

    c. Assigning service accounts to resources

    d. Managing IAM of a service account

    e. Managing service account impersonation

    e. Creating and managing short-lived service account credentials

5.3 Viewing audit logs

