## Introducing to Terraform for Google Cloud

- Explain the features and benefits of using Terraform. Which one of the following statements is true regarding Terraform?

  * [ ] Terraform uses the imperative approach to define infrastructure components.
  * [ ] Terraform is used to configure applications on Google Cloud.
  * [ ] Terraform can only be used for on-premises deployments.
  * [x] Terraform can be used for multi-cloud deployments.

- Explain use cases of Terraform for Google Cloud. Select the two use cases for Terraform.

  * [ ] Provide financial analytics
  * [ ] Run OS level customization
  * [ ] Provision an application
  * [x] Standardize configurations
  * [x] Automate changes

- Explain use cases of Terraform for Google Cloud. Select the three Terraform editions available in production.

  * [ ] Terraform Analytics
  * [ ] Terraform Cyber
  * [x] Terraform Enterprise
  * [x] Terraform Cloud
  * [x] Open source

- Define infrastructure as code. What is infrastructure as code (IaC)?

  * [ ] IaC is a data warehouse running on serverless infrastructure.
  * [ ] IaC is a cloud computing model that offers resources on demand to businesses and individuals by using the cloud.
  * [ ] IaC is a tool to maintain consistency in an application deployment environment.
  * [x] IaC is a process to define, provision, and manage cloud infrastructure by writing code in files.

## Terms and Concepts

- Create, update, and destroy Google Cloud resources using Terraform. In which phase of the Terraform workflow can you run pre-deployment checks against the policy library?

  * [x] Validate
  * [ ] Scope
  * [ ] Plan
  * [ ] Initialize

- Explain the purpose of Terraform commands Which command creates infrastructure resources?

  * [x] terraform apply
  * [ ] terraform plan
  * [ ] terraform init
  * [ ] terraform fmt

- Explain the Terraform workflow. In which phase of the Terraform workflow do you write configuration files based on the scope defined by your organization?

  * [ ] Scope
  * [x] Author
  * [ ] Initialize
  * [ ] Apply
  * [ ] Plan

## Writing Infrastructure Code for Google Cloud

- How many resource types can be represented in a single resource block?

  * [ ] Two
  * [x] One
  * [ ] Three
  * [ ] Four

- Can a variable be assigned values in multiple ways?

  * [ ] No
  * [x] Yes

- How can output values be used?

  * [ ] Parameterize a resource configuration.
  * [x] Print resource attributes.
  * [ ] Declare a resource within a Terraform configuration.

- Which dependency can be automatically detected by Terraform?

  * [ ] Explicit dependency
  * [x] Implicit dependency

## Organizing and Reusing Configuration with Terraform Modules

- State true or false. The source of a module can only be remote.

  * [ ] True
  * [x] False

- What is the purpose of output values within modules?

  * [ ] Initialize Terraform to download the plugins.
  * [ ] Parameterize a configuration.
  * [ ] Ensure that the syntax is in canonical format.
  * [x] Pass resource attributes outside a module.

- What happens when a version argument is specified in a module block?

  * [ ] Terraform automatically downgrades the module to the oldest version.
  * [ ] Terraform automatically downgrades the modules to the specific version.
  * [ ] Terrafomr automatically upgrades the modules to the specific version.
  * [x] Terraform automatically upgrades the module to the latest version matching the specified version constraint.

- Which code construct of Terraform helps you parameterize a configuration?

  * [ ] Resources
  * [ ] Modules
  * [ ] Output values
  * [x] Variables

## Introduction to Terraform State

- Select the three benefits of storing a Terraform state file remotely.

  * [x] Locking
  * [ ] Automatic insights
  * [ ] Usage analytics
  * [x] Sharing and delegation
  * [x] Secure access

- State true or false. A state file is stored by default in a local file named terraform.tfstate.

  * [ ] False
  * [x] True
