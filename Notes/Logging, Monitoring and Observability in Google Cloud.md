## Logging, Monitoring and Observability in Google Cloud

<div align="center">
<img width="650" src="https://user-images.githubusercontent.com/59575502/197404867-fb472195-12ec-4b7c-8a8d-ce1272c7282e.png">
</div>

### Operations-based tools
- Monitoring
- Logging
- Error Reporting
- Service Monitoring

#### Service monitoring
- Understand and troubleshoot intra-service dependencies 
- Current support for App Engine, Anthos Service Mesh, and Istio 
- Know when you're meeting or breaking SLOS Know when you have error budget to spend

![image](https://user-images.githubusercontent.com/59575502/197405081-70db1286-91e3-4ff0-807b-c6c90031ef42.png)

### Application performance management tools
- Debugger
- Trace
- Profiler

#### Debugger
- Real-time app debugging 
- Increased collaboration by sharing debug sessions 
- Debug snapshots, logpoints, conditional debugging 
- Integrations with popular IDEs 
- Multiple version control sources (GitHub, Cloud Source Repositories, Bitbucket, GitLab)

#### Trace
- Distributed latency analysis
- Support for App Engine, Compute Engine, and Google Kubernetes Engine 
- Near-real-time performance insights 
- In-depth latency reports 
- Find performance degradations in apps
- Automatic issue detection

#### Profiler
- Improve performance and reduce costs
- Low-impact production CPU and heap profiling
- Broad platform support (VMs, App Engine, Compute Engine, GKE)
- Support for Java, Go, Python, NodeJS
- Understand your applications' call patterns

<img width="600" align="right" src="https://user-images.githubusercontent.com/59575502/197405426-574d17af-f94b-4f79-9e7e-73bf61fe8681.png">

#### Why monitor?
Collecting, processing, aggregating, and displaying real-time quantitative data about a system, such as query counts and types, error counts and types, processing times, and server lifetimes 
- Continual improvement
- Dashboards
- Alerting
- Debugging

![image](https://user-images.githubusercontent.com/59575502/197405720-b0147827-9b90-475f-803f-77a7418b58ef.png)

<img width="500" align="left" src="https://user-images.githubusercontent.com/59575502/197405887-4a1f2140-a756-486b-9bf1-a7501facd964.png">

```Service level indicator``` - A ***quantifiable*** measure of service **reliability** </br>
```Service level objective``` - A ***reliability target*** for an SLI </br>
```Service level agreement``` - A contract between a service provider and a customer, defining the types and standards of services to be offered.

### Alerts
Alerts definedusing alerting policies. It has
- A name
- One or more conditions
- Notifications
- Documentation
- Supported notification channels include... (Email • SMS • Slack • GCP Mobile app • PagerDuty • Webhooks • Pub/Sub)

### Service Monitoring
Service Monitoring Helps with SLO and Alert Creation
- Accessed through the Google Cloud Console or the Service Monitoring API 
- Select latency or availability metrics to act as SLIS 
- Use SLls to easily create SLOS 
- Alerting easily integrated 
- Create and track error budgets

![image (1)](https://user-images.githubusercontent.com/59575502/197406554-943c112b-ec0f-4d47-bdbe-1fb0f47a54a9.png)

#### Error Budgets
- Zero error tolerance means zero updates 
- Error Budgets
  - Quantify the organization's tolerance for errors 
  - Operate like a currency or allowance 
  - Allow Devs to take calculated risks 
  - Excuse the occasional error 
  - Replenish over time

#### What Makes a Good Uptime Check?
- Protocol, host, and port are appropriate
- Response checked for specific content
- Check frequency proportional to criticality

#### OS Monitoring Agent
Gathers system and application metrics from VM instances and sends them to Monitoring
- Based on the open-source collected 
- Gathers additional system resources and application metrics 
- Optional, but recommended 
- Supports third-party applications, such as:
  - Apache/Nginx/MySQL 
- Additional support offered through BindPlane from Blue Medora 
- Supports major operating systems:
  - CentOS, Debian,Red Hat Enterprise Linux 
  - Ubuntu LTS, SUSE Linux Enterprise Server 
  - Windows server

#### Services with “Other” Monitoring Support
Don't try to manually install or configure the agent 
- App Engine standard, has monitoring built-in 
- App Engine flex, agent pre-installed and configured 
- GKE nodes, monitoring configurable and enabled by default 
- Anthos GKE On-Prem, agent collects system but not application metrics 
- Cloud Run provides integrated monitoring support 
- Cloud Function supports integrated monitoring

#### OS Logging Agent
Streams logs from common third-party applications and system software to Google Cloud Logging
- Supports third-party applications, such as:
  - Apache/Tomcat/Nginx 
  - Chef/Jenkins/Puppet
  - Cassandra/Mongodb/MySQL 
- Based on fluentd log data collector – can add own fluentd configuration files 
- Supports major operating systems:
  - CentOS
  - Debian 
  - Red Hat Enterprise Linux 
  - Ubuntu LTS 
  - Suse 
  - Windows server

#### Services with “Other” Logging Support
Don't try to manually install or configure the agent 
- App Engine flex and standard have built-in support for logging 
- GKE nodes, can enable GKE logging 
- Anthos GKE On-Prem agent collects system but not app logs 
- Cloud Run has built-in logging support 
- Cloud Functions have built-in logging support

### What is Prometheus?
- Prometheus is an optional monitoring tool for Kubernetes
  - Supported with GKE Monitoring 
- Service metrics using Prometheus exposition format can be exported and made visible as external metrics

### Exposing Custom Metrics
Two fundamental approaches:
- Use the Cloud Monitoring API 
- Use OpenCensus

### What is OpenCensus?
- Open-source library to help capture, manipulate, and export traces and metrics
  - Works with microservices and monoliths 
- Supports many mainstream languages
  - Java, Python, Node.js, Go, C#, Erlang, and C++ 
- Low overhead and broadly supported

![image](https://user-images.githubusercontent.com/59575502/197849044-0e597b4d-d453-45ee-b620-8d70425e572f.png)

### Labels and logs
- Allows for log-based metrics to contain a time series for each label 
- Two types of labels applied:
  - Default
  - User-defined
- User-defined labels can be either of the following:
  - The entire contents of a named field in the LogEntry object 
- A part of a named field that matches a regular expression
- You can create up to 10 user-defined labels per metric
- A label cannot be deleted once created
  - And will grow time series significantly

![image (1)](https://user-images.githubusercontent.com/59575502/197850232-c94a2c1e-9ac4-49ee-b5d2-2d8636278523.png)

### Use [VPC Flow Logs](https://cloud.google.com/vpc/docs/using-flow-logs)
VPC Flow Logs records a sample of network flows sent from and received by VM instances, including instances used as GKE nodes. These logs can be used for network monitoring, forensics, real-time security analysis, and expense optimization.

### Cloud NAT logging
- Allows you to log NAT connections and/or errors
  - TCP and UDP traffic only
  - 50-100 entries per second, per vCPU 
- Enable logging by editing the Cloud NAT settings
- View by filtering Logs Explorer: 
  - Resource: Cloud NAT Gateway 
  - (optional) Restrict to region or NAT Gateway

#### Packet Mirroring: visualize and protect your data
• Clones VPC instance traffic and forwards for examination 
• Happens at NIC not as part of VPC 
• Can monitor and analyze security status 
• Provides access to full traffic flow for regulatory or performance analysis

<img width="600" align="right" src="https://user-images.githubusercontent.com/59575502/197852011-5d6db97c-1b49-49b3-ab91-49dfdc4689a5.png">

### Network Intelligence Center
Centralized Network monitoring and visibility
- ```Topology``` - view VPC topology and associated metrics
- ```Connectivity Tests``` - Evaluate connectivity to and from VPC resources
- ```Performance Dashboard``` - VPC packet loss and latency metrics
- ```Firewall Insights``` - Visibility into firewall usage and configuration issues


<img width="1281" alt="Screenshot 2022-10-25 at 11 57 23 PM" src="https://user-images.githubusercontent.com/59575502/197852679-f38a0062-148f-4bf3-983b-f9faaeabd35d.png">

















