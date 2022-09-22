## Identity and Access Management
- What abstraction is primarily used to administer user access in IAM ?

  * [ ] Leases, an abstraction of periodic entitlements.
  * [x] Roles, an abstraction of job roles.
  * [ ] Credentials, an abstraction of an authorization token.
  * [ ] Privileges, an abstraction of access rights.

- Which of the following is not a type of IAM role?

  * [ ] Basic
  * [x] Advanced
  * [ ] Predefined
  * [ ] Custom

- Which of the following is not a type of IAM member?

  * [ ] Google Workspace domain
  * [ ] Google Group
  * [ ] Cloud Identity domain
  * [ ] Google Account
  * [ ] Service Account
  * [x] Organization Account

## Storage and Database Services
- What data storage service might you select if you just needed to migrate a standard relational database running on a single machine in a datacenter to the cloud?

  * [x] Cloud SQL
  * [ ] BigQuery
  * [ ] Persistent Disk
  * [ ] Cloud Storage

- Which Google Cloud data storage service offers ACID transactions and can scale globally?

  * [ ] Cloud Storage
  * [ ] Cloud CDN
  * [x] Cloud Spanner
  * [ ] Cloud SQL

- Which data storage service provides data warehouse services for storing data but also offers an interactive SQL interface for querying the data?

  * [x] BigQuery
  * [ ] Dataproc
  * [ ] Datalab
  * [ ] Cloud SQL

## Resource Management
- No resources in Google Cloud can be used without being associated with...

  * [ ] A bucket.
  * [ ] A user.
  * [ ] A virtual machine.
  * [x] A project.

- A budget is set at $500 and an alert is set at 100%. What happens when the full amount is used?

  * [ ] Nothing. There is no point in sending a notification when there is no budget remaining.
  * [x] A notification email is sent to the Billing Administrator.
  * [ ] You have a 4-hour courtesy period before Google shuts down all resources.
  * [ ] Everything in the associated project will be suspended because there is no more budget to spend.

- How do quotas protect Google Cloud customers?

  * [ ] By preventing resource use of too many different Google Cloud services.
  * [ ] By preventing resource use by unknown users.
  * [ ] By preventing resource use in too many zones in a region.
  * [x] By preventing uncontrolled consumption of resources.

## Resource Monitoring
- What is the foundational process at the base of Google's Site Reliability Engineering (SRE) ?

  * [ ] Capacity planning.
  * [ ] Testing and release procedures.
  * [x] Monitoring.
  * [ ] Root cause analysis.

- What is the purpose of the Cloud Trace service?

  * [x] Reporting on latency as part of managing performance.
  * [ ] Reporting on Google Cloud system errors.
  * [ ] Reporting on application errors.
  * [ ] Reporting on Google Cloud resource consumption as part of managing performance.

- Google Cloud’s operations suite integrates several technologies, including monitoring, logging, error reporting, and debugging that are commonly implemented in other environments as separate solutions using separate products. What are key benefits of integration of these services?

  * [x] Reduces overhead, reduces noise, streamlines use, and fixes problems faster
  * [ ] Ability to replace one tool with another from a different vendor
  * [ ] Detailed control over the connections between the technologies
  * [ ] Better for Google Cloud only so long as you don't need to monitor other applications or clouds
