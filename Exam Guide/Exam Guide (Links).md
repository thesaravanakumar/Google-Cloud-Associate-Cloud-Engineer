## Section 1. Setting up a cloud solution environment
### 1.1 Setting up cloud projects and accounts. Activities include:

  - (a) Creating a resource hierarchy </br>

  - (b) Applying organizational policies to the resource hierarchy </br>

  - (c) Granting members IAM roles within a project </br>
https://cloud.google.com/sdk/gcloud/reference/projects/add-iam-policy-binding
  - (d) Managing users and groups in Cloud Identity (manually and automated) </br>
https://support.google.com/cloudidentity/answer/7319251?hl=en
  - (e) Enabling APIs within projects </br>
https://cloud.google.com/service-management/enable-disable
https://cloud.google.com/sdk/gcloud/reference/services/
https://cloud.google.com/sdk/gcloud/reference/services/list
https://cloud.google.com/sdk/gcloud/reference/services/enable
https://cloud.google.com/sdk/gcloud/reference/services/disable

  - (f) Provisioning and setting up products in Google Cloud’s operations suite </br>
https://cloud.google.com/monitoring/accounts/

### 1.2 Managing billing configuration. Activities include:

  - (a) Creating one or more billing accounts </br>
https://cloud.google.com/billing/docs/how-to/manage-billing-account
  - (b) Linking projects to a billing account </br>
https://cloud.google.com/sdk/gcloud/reference/beta/billing/projects/link
  - (c) Establishing billing budgets and alerts </br>
https://cloud.google.com/billing/docs/how-to/budgets
  - (d) Setting up billing exports </br>
https://cloud.google.com/billing/docs/how-to/export-data-file
https://cloud.google.com/billing/docs/how-to/export-data-bigquery
https://cloud.google.com/billing/docs/how-to/bq-examples

### 1.3 Installing and configuring the command line interface (CLI), specifically the Cloud SDK (e.g., setting the default project).
Install:
- https://hub.docker.com/r/google/cloud-sdk/~/dockerfile/
- https://cloud.google.com/sdk/docs/quickstart-linux
```
# To set the project property in the core section, run:
 $ gcloud config set project myProject

# To set the zone property in the compute section, run:
 $ gcloud config set compute/zone asia-east1-b
```
## Section 2. Planning and configuring a cloud solution

### 2.1 Planning and estimating Google Cloud product use using the Pricing Calculator
https://cloud.google.com/products/calculator/
[Google Cloud Platform on a shoestring budget (Google I/O '18)](https://youtu.be/N2OG1w6bGFo)

### 2.2 Planning and configuring compute resources. Considerations include:

  - (a) Selecting appropriate compute choices for a given workload (e.g., Compute Engine, Google Kubernetes Engine, Cloud Run, Cloud Functions) </br>
[Deciding between Compute Engine, Container Engine, App Engine and more (Google Cloud Next '17)](https://www.youtube.com/watch?v=g0dN8Hkh5H8)
```Compute Engine``` - It's VM. So you have full control to do whatever you need to do to connect things together.
It's also a really good fit for existing systems.
```Kubernetes Engine``` - Container Engine is a system of containers working together to solve your problems.
```App Engine``` - App Engine is focused on making your web code run extremely well. It's optimized for that. And it's code first kind of thinking.

  - (b) Using preemptible VMs and custom machine types as appropriate </br>
```
# CREATE INSTANCE WITH 4 vCPUs and 5 GB MEMORY
gcloud compute instances create my-vm --custom-cpu 4 --custom-memory 5

# ENABLE PREEMPTIBLE OPTION
gcloud compute instances create my-vm --zone us-central1-b --preemptible
```
### 2.3 Planning and configuring data storage options. Considerations include:
[A map of storage options in Google Cloud](https://cloud.google.com/blog/topics/developers-practitioners/map-storage-options-google-cloud)
[From blobs to relational tables: Where do I store my Data? (Google Cloud Next '17)](https://youtu.be/rn_68hBqt20)
  - (a) Product choice (e.g., Cloud SQL, BigQuery, Firestore, Cloud Spanner, Cloud Bigtable) </br>
https://cloud.google.com/sql/docs/
https://cloud.google.com/bigquery/
https://cloud.google.com/spanner/
https://cloud.google.com/bigtable/
  - (b) Choosing storage options (e.g., Zonal persistent disk, Regional balanced persistent disk, Standard, Nearline, Coldline, Archive) </br>
https://cloud.google.com/storage/docs/gsutil/commands/mb
https://cloud.google.com/storage/docs/storage-classes
### 2.4 Planning and configuring network resources. Tasks include:

  - (a) Differentiating load balancing options </br>
https://cloud.google.com/files/internal-load-balancing-tutorial-slides.pdf
https://cloud.google.com/compute/docs/load-balancing/internal/

  - (b) Identifying resource locations in a network for availability </br>

  - (c) Configuring Cloud DNS </br>
https://cloud.google.com/dns/quickstart
## Section 3. Deploying and implementing a cloud solution

### 3.1 Deploying and implementing Compute Engine resources. Tasks include:

  - (a) Launching a compute instance using the Google Cloud console and Cloud SDK (gcloud) (e.g., assign disks, availability policy, SSH keys) </br>
https://cloud.google.com/sdk/gcloud/reference/compute/instances/create
https://cloud.google.com/sdk/gcloud/reference/compute/instances/attach-disk

  - (b) Creating an autoscaled managed instance group using an instance template </br>
https://cloud.google.com/compute/docs/autoscaler/#managed_instance_groups
https://cloud.google.com/compute/docs/instance-groups/
https://cloud.google.com/compute/docs/instance-templates/

You can create two types of managed instance groups:
A zonal managed instance group, which contains instances from the same zone.
A regional managed instance group, which contains instances from multiple zones across the same region.

  - (c) Generating/uploading a custom SSH key for instances </br>
https://cloud.google.com/compute/docs/instances/adding-removing-ssh-keys
  - (d) Installing and configuring the Cloud Monitoring and Logging Agent </br>
https://cloud.google.com/monitoring/agent/install-agent
https://cloud.google.com/logging/docs/agent/installation
  - (e) Assessing compute quotas and requesting increases </br>
https://console.cloud.google.com/iam-admin/quotas?project=xxx
https://cloud.google.com/compute/quotas
https://cloud.google.com/appengine/quotas
https://cloud.google.com/pubsub/quotas
https://cloud.google.com/bigquery/quotas
https://cloud.google.com/bigquery/docs/custom-quotas
https://cloud.google.com/functions/quotas
https://cloud.google.com/datastore/pricing
https://cloud.google.com/deployment-manager/pricing-and-quotas
https://cloud.google.com/monitoring/quotas
https://cloud.google.com/logging/quotas
https://cloud.google.com/endpoints/docs/openapi/quotas-configure

### 3.2 Deploying and implementing Google Kubernetes Engine resources. Tasks include:

  - (a) Installing and configuring the command line interface (CLI) for Kubernetes (kubectl) </br>

  - (b) Deploying a Google Kubernetes Engine cluster with different configurations including AutoPilot, regional clusters, private clusters, etc. </br>
https://cloud.google.com/kubernetes-engine/docs/how-to/creating-a-container-cluster
https://cloud.google.com/kubernetes-engine/docs/concepts/cluster-architecture

  - (c) Deploying a containerized application to Google Kubernetes Engine </br>
```
gcloud config set container/cluster [CLUSTER_NAME]
gcloud container clusters get-credentials [CLUSTER_NAME]
```
  - (d) Configuring Google Kubernetes Engine monitoring and logging </br>
https://kubernetes.io/docs/tasks/debug-application-cluster/logging-stackdriver/
```
gcloud beta container clusters update --logging-service=none CLUSTER
kubectl get ds fluentd-gcp-v2.0 --namespace kube-system -o yaml > fluentd-gcp-ds.yaml
kubectl replace -f fluentd-gcp-ds.yaml
```

### 3.3 Deploying and implementing Cloud Run and Cloud Functions resources. Tasks include, where applicable:

  - (a) Deploying an application and updating scaling configuration, versions, and traffic splitting </br>
https://cloud.google.com/appengine/docs/standard/python/how-instances-are-managed
https://cloud.google.com/appengine/docs/admin-api/deploying-apps
https://cloud.google.com/sdk/gcloud/reference/app/services/set-traffic
    - ```Scaling``` - The type you assign to a service determines the whether its instances are resident or dynamic:
      - ```Manual scaling``` - A service with manual scaling use resident instances that continuously run the specified number of instances irrespective of the load level. This allows tasks such as comple initializations and applications that rely on the state of the memory over time.
      - ```Automatic scaling``` - Auto scaling services use dynamic instances that get created based on request rate, response latencies, and other application metrics. However, if you specify a number of minimum idle instances, that specified number of instances run as resident instances while any additional instances are dynamic.
      - ```Basic Scaling``` - A service with basic scaling use dynamic instances. Each instance is created when the application receives a request. The instance will be turned down when the app becomes idle. Basic scaling is ideal for work that is intermittent or driven by user activity.
    - ```Versions``` - The recommended approach is to remove the version element from your app.yaml file and instead, use a command-line flag to specify your version ID:
```
gcloud app deploy -v [YOUR_VERSION_ID]
appcfg.py update -V [YOUR_VERSION_ID]
```

  - (b) Deploying an application that receives Google Cloud events (e.g., Pub/Sub events, Cloud Storage object change notification events) </br>
https://cloud.google.com/functions/docs/tutorials/pubsub
https://cloud.google.com/functions/docs/calling/storage
### 3.4 Deploying and implementing data solutions. Tasks include:

  - (a) Initializing data systems with products (e.g., Cloud SQL, Firestore, BigQuery, Cloud Spanner, Pub/Sub, Cloud Bigtable, Dataproc, Dataflow, Cloud Storage) </br>

  - (b) Loading data (e.g., command line upload, API transfer, import/export, load data from Cloud Storage, streaming data to Pub/Sub) </br>
https://cloud.google.com/storage/transfer/reference/rest/
https://cloud.google.com/sql/docs/mysql/import-export/
https://cloud.google.com/sql/docs/postgres/import-export/importing
https://cloud.google.com/sql/docs/postgres/import-export/
https://cloud.google.com/datastore/docs/export-import-entities
https://cloud.google.com/pubsub/docs/quickstart-cli

### 3.5 Deploying and implementing networking resources. Tasks include:

  - (a) Creating a VPC with subnets (e.g., custom-mode VPC, shared VPC) </br>

  - (b) Launching a Compute Engine instance with custom network configuration (e.g., internal-only IP address, Google private access, static external and private IP address, network tags) </br>
https://cloud.google.com/sdk/gcloud/reference/compute/networks/subnets/create
https://cloud.google.com/sdk/gcloud/reference/compute/networks/subnets/create
  - (c) Creating ingress and egress firewall rules for a VPC (e.g., IP subnets, network tags, service accounts) </br>
https://cloud.google.com/sdk/gcloud/reference/compute/firewall-rules/
  - (d) Creating a VPN between a Google VPC and an external network using Cloud VPN </br>
https://cloud.google.com/vpn/docs/concepts/overview
https://cloud.google.com/vpn/docs/how-to/creating-vpns

  - (e) Creating a load balancer to distribute application network traffic to an application (e.g., Global HTTP(S) load balancer, Global SSL Proxy load balancer, Global TCP Proxy load balancer, regional network load balancer, regional internal load balancer) </br>
https://cloud.google.com/compute/docs/load-balancing/http/
https://cloud.google.com/compute/docs/load-balancing/tcp-ssl/
https://cloud.google.com/compute/docs/load-balancing/tcp-ssl/tcp-proxy
https://cloud.google.com/compute/docs/load-balancing/network/
https://cloud.google.com/solutions/internal-load-balancing-haproxy

### 3.6 Deploying a solution using Cloud Marketplace. Tasks include:

  - (a) Browsing the Cloud Marketplace catalog and viewing solution details </br>
https://console.cloud.google.com/launcher
  - (b) Deploying a Cloud Marketplace solution </br>
https://console.cloud.google.com/launcher
### 3.7 Implementing resources via infrastructure as code. Tasks include:

  - (a) Building infrastructure via Cloud Foundation Toolkit templates and implementing best practices </br>

  - (b) Installing and configuring Config Connector in Google Kubernetes Engine to create, update, delete, and secure resources </br>

## Section 4. Ensuring successful operation of a cloud solution

### 4.1 Managing Compute Engine resources. Tasks include:

  - (a) Managing a single VM instance (e.g., start, stop, edit configuration, or delete an instance) </br>
https://cloud.google.com/sdk/gcloud/reference/compute/instances/start
https://cloud.google.com/sdk/gcloud/reference/compute/instances/stop
https://cloud.google.com/sdk/gcloud/reference/compute/instances/delete

  - (b) Remotely connecting to the instance </br>
https://cloud.google.com/compute/docs/instances/connecting-to-instance
  - (c) Attaching a GPU to a new instance and installing necessary dependencies </br>

You can attach GPUs only to instances with a predefined machine type or custom machine type that you are able to create in a zone. GPUs are not supported on shared-core machine types or memory-optimized machine types.
</br>
https://cloud.google.com/compute/docs/gpus/add-gpus
- ```ACCELERATOR_COUNT``` is the number of GPUs that you want to add to your instance. See GPUs on Compute Engine for a list of GPU limits based on the machine type of your instance.
- ```ACCELERATOR_TYPE``` is the GPU model that you want to use. See GPUs on Compute Engine for a list of available GPU models.


  - (d) Viewing current running VM inventory (instance IDs, details) </br>

  - (e) Working with snapshots (e.g., create a snapshot from a VM, view snapshots, delete a snapshot) </br>
https://cloud.google.com/compute/docs/disks/create-snapshots
https://cloud.google.com/sdk/gcloud/reference/compute/disks/create
</br>
A source snapshot used to create the disks. It is safe to delete a snapshot after a disk has been created from the snapshot. In such cases, the disks will no longer reference the deleted snapshot. To get a list of snapshots in your current project, run gcloud compute snapshots list. A snapshot from an existing disk can be created using the gcloud compute disks snapshot command. This flag is mutually exclusive with --image.
When using this option, the size of the disks must be at least as large as the snapshot size. Use --size to adjust the size of the disks.
https://cloud.google.com/sdk/gcloud/reference/compute/snapshots/list
https://cloud.google.com/sdk/gcloud/reference/compute/snapshots/delete

  - (f) Working with images (e.g., create an image from a VM or a snapshot, view images, delete an image) </br>
https://cloud.google.com/sdk/gcloud/reference/compute/images/create
https://cloud.google.com/sdk/gcloud/reference/compute/images/list
https://cloud.google.com/sdk/gcloud/reference/compute/images/delete

  - (g) Working with instance groups (e.g., set autoscaling parameters, assign instance template, create an instance template, remove instance group) </br>
https://cloud.google.com/compute/docs/instance-groups/
https://cloud.google.com/compute/docs/instance-groups/updating-managed-instance-groups
https://cloud.google.com/compute/docs/instance-templates/
https://cloud.google.com/compute/docs/instance-templates/create-instance-templates
https://cloud.google.com/sdk/gcloud/reference/compute/instance-groups/managed/create
https://cloud.google.com/sdk/gcloud/reference/compute/instance-groups/managed/delete

  - (h) Working with management interfaces (e.g., Google Cloud console, Cloud Shell, Cloud SDK) </br>

### 4.2 Managing Google Kubernetes Engine resources. Tasks include:
https://kubernetes.io/docs/reference/kubectl/cheatsheet/
  - (a) Viewing current running cluster inventory (nodes, pods, services) </br>
```
kubectl get nodes
kubectl get pods
kubectl get services
```

  - (b) Browsing Docker images and viewing their details in the Artifact Registry </br>

  - (c) Working with node pools (e.g., add, edit, or remove a node pool) </br>
https://cloud.google.com/kubernetes-engine/docs/how-to/resizing-a-container-cluster
https://cloud.google.com/sdk/gcloud/reference/container/clusters/resize
  - (d) Working with pods (e.g., add, edit, or remove pods) </br>

  - (e) Working with services (e.g., add, edit, or remove a service) </br>

  - (f) Working with stateful applications (e.g. persistent volumes, stateful sets) </br>

  - (g) Managing Horizontal and Vertical autoscaling configurations </br>

  - (h) Working with management interfaces (e.g., Google Cloud console, Cloud Shell, Cloud SDK, kubectl) </br>

### 4.3 Managing Cloud Run resources. Tasks include:

  - (a) Adjusting application traffic-splitting parameters </br>

  - (b) Setting scaling parameters for autoscaling instances </br>

  - (c) Determining whether to run Cloud Run (fully managed) or Cloud Run for Anthos </br>

### 4.4 Managing storage and database solutions. Tasks include:

  - (a) Managing and securing objects in and between Cloud Storage buckets </br>

  - (b) Setting object life cycle management policies for Cloud Storage buckets </br>

  - (c) Executing queries to retrieve data from data instances (e.g., Cloud SQL, BigQuery, Cloud Spanner, Datastore, Cloud Bigtable) </br>

  - (d) Estimating costs of data storage resources </br>
https://cloud.google.com/bigquery/docs/estimate-costs
  - (e) Backing up and restoring database instances (e.g., Cloud SQL, Datastore) </br>

  - (f) Reviewing job status in Dataproc, Dataflow, or BigQuery </br>

### 4.5 Managing networking resources. Tasks include:

  - (a) Adding a subnet to an existing VPC </br>
https://cloud.google.com/vpc/docs/using-vpc
</br>
Adding a new subnet to an existing VPC network
You can add a subnet to a region of an existing VPC network. The primary IP range of this new subnet cannot overlap the IP range of existing subnets in the current network, in peered VPC networks, or in on-premises networks connected via VPN or Interconnect.

You can optionally assign a secondary IP range to the subnet for use with Alias IP. The secondary IP range also cannot overlap the IP ranges of existing connected subnets.</br>
```
gcloud compute networks subnets create [SUBNET_NAME] \
--network [NETWORK] \
--range [IP_RANGE] \
[--secondary-range [RANGE_NAME]=[2ND_IP_RANGE]
```
  - (b) Expanding a subnet to have more IP addresses </br>
You can expand the IP range of a subnet. You cannot shrink it.
Restrictions:
    - The new subnet must not overlap with other subnets in the same VPC network in any region.
    - The new subnet must stay inside the RFC 1918 address spaces.
    - The new network range must be larger than the original, which means the prefix length value must be a smaller number.
    - Auto mode subnets start with a /20 IP range. They can be expanded to a /16, but no larger.
```
gcloud compute networks subnets expand-ip-range [SUBNET_NAME] \
--region [REGION] \
--prefix-length [PREFIX_LENGTH]
```
  - (c) Reserving static external or internal IP addresses </br>
https://cloud.google.com/compute/docs/ip-addresses/reserve-static-external-ip-address
https://cloud.google.com/compute/docs/ip-addresses/reserve-static-internal-ip-address
  - (d) Working with CloudDNS, CloudNAT, Load Balancers and firewall rules </br>

### 4.6 Monitoring and logging. Tasks include:

  - (a) Creating Cloud Monitoring alerts based on resource metrics </br>
https://cloud.google.com/monitoring/custom-metrics/creating-metrics
  - (b) Creating and ingesting Cloud Monitoring custom metrics (e.g., from applications or logs) </br>
https://cloud.google.com/monitoring/custom-metrics/
https://cloud.google.com/monitoring/api/v3/metrics-details

  - (c) Configuring log sinks to export logs to external systems (e.g., on-premises or BigQuery) </br>

  - (d) Configuring log routers </br>

  - (e) Viewing and filtering logs in Cloud Logging </br>

  - (f) Viewing specific log message details in Cloud Logging </br>

  - (g) Using cloud diagnostics to research an application issue (e.g., viewing Cloud Trace data, using Cloud Debug to view an application point-in-time) </br>

  - (h) Viewing Google Cloud status </br>

## Section 5. Configuring access and security

### 5.1 Managing Identity and Access Management (IAM). Tasks include:

  - (a) Viewing IAM policies </br>
https://cloud.google.com/sdk/gcloud/reference/projects/get-iam-policy
https://cloud.google.com/sdk/gcloud/reference/organizations/get-iam-policy


  - (b) Creating IAM policies </br>
https://cloud.google.com/sdk/gcloud/reference/projects/set-iam-policy
https://cloud.google.com/sdk/gcloud/reference/projects/add-iam-policy-binding
https://cloud.google.com/sdk/gcloud/reference/organizations/set-iam-policy
https://cloud.google.com/sdk/gcloud/reference/organizations/add-iam-policy-binding

  - (c) Managing the various role types and defining custom IAM roles (e.g., primitive, predefined and custom) </br>
https://cloud.google.com/iam/docs/creating-custom-roles
https://cloud.google.com/sdk/gcloud/reference/iam/roles/
https://cloud.google.com/sdk/gcloud/reference/iam/roles/create
https://cloud.google.com/iam/reference/rest/v1/projects.roles

### 5.2 Managing service accounts. Tasks include:
https://cloud.google.com/compute/docs/access/service-accounts
  - (a) Creating service accounts </br>

  - (b) Using service accounts in IAM policies with minimum permissions </br>
**Best practices:**
In general, Google recommends that each instance that needs to call a Google API should run as a service account with the minimum permissions necessary for that instance to do its job. In practice, this means you should configure service accounts for your instances with the following process:
Create a new service account rather than using the Compute Engine default service account.
Grant IAM roles to that service account for only the resources that it needs.
Configure the instance to run as that service account.
Grant the instance the [googleapis.com/auth/cloud-platform](https://www.googleapis.com/auth/cloud-platform) scope.
Avoid granting more access than necessary and regularly check your service account permissions to make sure they are up-to-date.

  - (c) Assigning service accounts to resources </br>
https://cloud.google.com/compute/docs/access/create-enable-service-accounts-for-instances
  - (d) Managing IAM of a service account </br>

  - (e) Managing service account impersonation </br>

  - (e) Creating and managing short-lived service account credentials </br>

### 5.3 Viewing audit logs
Cloud Audit Logging returns two types of logs:
- ```Admin activity logs:``` Contains log entries for operations that modify the configuration or metadata of a Compute Engine resource. Any API call that modifies a resource such as creation, deletion, updating, or modifying a resource using a custom verb fall into this category.
- ```Data access logs:``` Contains log entries for operations that perform read-only operations do not modify any data, such as get, list, and aggregated list methods. Unlike audit logs for other services, Compute Engine only has ADMIN_READ data access logs and do not generally offer DATA_READ and DATA_WRITE logs. This is because DATA_READ and DATA_WRITE logs are only used for services that store and manage user data such as Google Cloud Storage, Google Cloud Spanner, and Google Cloud SQL, which does not apply to Compute Engine. There is one exception to this rule: the instance.getSerialPortOutput does generate a DATA_READ log because the method reads data directly from the VM instance.</br>
https://cloud.google.com/compute/docs/audit-logging
