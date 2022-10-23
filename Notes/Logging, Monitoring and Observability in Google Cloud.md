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































