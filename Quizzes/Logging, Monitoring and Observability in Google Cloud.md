## Introduction to Monitoring in Google Cloud

- The error-reporting tool is showing occasional errors in your service and you don’t know why. Which tool below would help track down your programming error?

  * [ ] Logging
  * [ ] Trace
  * [x] Debugger
  * [ ] Profiler

- You want a simple way to see the latency of requests for a web application you deployed to App Engine. What GCP tool should you use?

  * [ ] Logging
  * [x] Trace
  * [ ] Debugger
  * [ ] Profiler

- You want to do analytics on the most frequently used features of your application. Which tool might be best for doing this?

  * [x] Logging
  * [ ] Trace
  * [ ] Debugger
  * [ ] Profiler

## Avoiding Customer Pain

- What are the four golden signals?

  * [ ] Availability, durability, scalability, resiliency.
  * [ ] IKPIs, SLIs, SLOs, SLAs.
  * [ ] Get, post, put, delete.
  * [x] Latency, traffic, saturation, errors.

- Which of the following is NOT true when talking about error budgets?

  * [ ] Developers can work on new features as long as they are within their error budget
  * [ ] You should devise an alerting strategy that notifies developers of an event that is consuming an unusually high percentage to the error budget.
  * [ ] The error budget is calculated as 100% minus the SLO for a given SLI.
  * [x] An error budget is generally expressed as a percentage, and that percentage will hover somewhere near, but not at, 100%.

- Which definition below best describes an SLI

  * [x] It is a time-bound measurable attribute of a service.
  * [ ] It is a key performance indicator, for example, clicks per session or customer signups.
  * [ ] It represents a contract with your customers regarding service performance.
  * [ ] It is a percentage goal of a measure you intend your service to achieve.

## Alerting Policies

- In evaluating your alerting policies, which below best describes recall.

  * [ ] How long it takes to send notifications in various conditions
  * [ ] The proportion of alerts detected that were relevant to the sum of relevant and irrelevant alerts
  * [x] The proportion of alerts detected that were relevant to the sum of relevant alerts and missed alerts
  * [ ] How long alerts fire after an issue is resolved

- In evaluating your alerting policies, which below best describes precision.

  * [ ] How long it takes to send notifications in various conditions
  * [ ] The proportion of events detected that were significant
  * [x] The proportion of significant events detected
  * [ ] How long alerts fire after an issue is resolved

- In Google Cloud alerting, which of the options below is NOT a valid notification channel?

  * [ ] Slack
  * [ ] SMS and Email
  * [ ] Webhooks
  * [x] Twitter

## Monitoring Critical Systems

- You want to be notified if your application is down. Which GCP tool makes this easy?

 * [ ] Readiness Probe
 * [ ] Liveness Probe
 * [ ] Health Check
 * [x] Uptime Check

- Which option below is NOT a feature of Google Cloud monitoring dashboards?

 * [ ] Can create workspaces to monitor resources in different projects.
 * [x] Does not require the Monitoring Viewer role..
 * [ ] Can monitor resources in AWS and on-prem as well as GCP.
 * [ ] Automated predefined dashboards based on project resources.

- You’re setting up a load balancer for an application you deployed to Compute Engine. To ensure the load balancer only sends requests to machines that are working; you would use what GCP tool?

 * [ ] Readiness Probe
 * [ ] Liveness Probe
 * [x] Health Check
 * [ ] Uptime Check

## Configuring Google Cloud Services for Observability

- Which statement below is false?

 * [ ] Workspaces can include resources from multiple projects.
 * [ ] You can allow other users to view your workspace using IAM.
 * [x] Each project can be in only one workspace.
 * [ ] Workspaces can include AWS resources.

- You’ve deployed an application to Compute Engine. The application writes to the logs, but you can’t find any of the logged messages in Google Cloud Logging. What might be the problem?

 * [ ] You need to deny access to all Google Cloud services under scopes.
 * [ ] You need to add the Logging Viewer role to the service account.
 * [x] You need to install the logging agent.
 * [ ] You need to turn on the VM machine logs.

- Management wants to see analysis of resources by the development team, department, cost center, and application status. What could you do to make this easier?

 * [ ] Add appropriate tags to your Google Cloud resources.
 * [ ] Use customized logging messages that include appropriate resource metadata.
 * [x] Add appropriate labels to your Google Cloud resource.
 * [ ] Use standardized prefixes on the names of all resources.

## Advanced Logging and Analysis

- Your governance team has mandated you save your log data for 5 years for compliance reasons. Where would the best place to export it be?

 * [x] Cloud Storage in a single-region bucket using the archival storage class
 * [ ] BigQuery
 * [ ] You don’t need to export it, just set the retention policy in Logging to 5 years
 * [ ] Cloud Storage in a multi-region bucket

- You want to use the logs to monitor application usage in real time. Where would the best export sink be?

 * [x] Pub/Sub
 * [ ] BigQuery
 * [ ] Spanner
 * [ ] Cloud Storage

- Your manager wants a daily report of resource utilization by application. Where would the best export sink be?

 * [ ] Pub/Sub
 * [x] BigQuery
 * [ ] Spanner
 * [ ] Cloud Storage

## Monitoring Network Security and Audit Logs

- Which of the statements below are FALSE when explaining why Data Access logs are turned off by default?

 * [ ] Can be very large.
 * [ ] May contain sensitive information.
 * [x] They often have VPC access issues.
 * [ ] Can be expensive to store.

- If you want to provide an external auditor access to your logs, what IAM role would be best?

 * [ ] Project Viewer
 * [ ] Project Editor
 * [x] Logging Viewer
 * [ ] Logging Admin

## Managing Incidents

- Which of the following documents summarize the events during the incident and evaluate the effectiveness of the incident response?

 * [ ] Alerts
 * [ ] Communication Channels
 * [ ] Support tickets
 * [x] Postmortems

- Which of the following is the most important task after an incident has been declared?

 * [ ] Postmortem
 * [ ] Root cause analysis
 * [ ] Assign blame
 * [x] Mitigation

- Which of the following are incident response team roles?

 * [ ] On-call Responder, Helpdesk, DevOps
 * [ ] Executive, Operations, Lead
 * [ ] Helpdesk, DevOps, Engineering
 * [x] Incident Commander, Operations Lead, Communications Lead

## Investigating Application Performance Issues

- Your App Engine application crashes sometimes and you don’t know why. It works on your development machine. Which tool would most likely help you figure out the problem?

 * [ ] Profiler
 * [ ] Trace
 * [ ] Logging
 * [x] Debugger

- You’ve deployed a new version of a service and all of a sudden significantly more instances are being created in your Kubernetes cluster. You service scales when average CPU utilization is greater than 70%. What tool would help you investigate the problem?

 * [x] Profiler
 * [ ] Trace
 * [ ] Logging
 * [ ] Debugger

- You have an SLO that states 90% of your http requests need to respond in under 100 ms. You’d like a report that compares latency for your last two versions. What tool would you use to most easily create this report?

 * [ ] Profiler
 * [x] Trace
 * [ ] Logging
 * [ ] Debugger

