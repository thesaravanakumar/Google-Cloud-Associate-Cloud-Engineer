## Getting Started with Terraform for Google Cloud

#### What is infrastructure as code (laC)?
Instead of clicking around a web UI or using SSH to connect to a server and manually executing commands, with lac you can write code in files to define, provision, and manage your infrastructure.

#### DevOps
- Emphasizes the collaboration and communication of both software developers and IT operations teams
- Automate the process of software delivery and infrastructure changes

##### Benefits of lac
- ```Declarative``` - Specify the desired state of infrastructure, not updates.
- ```Code management``` - Commit, version, trace, and collaborate, just like source code.
- ```Auditable``` - Compare infrastructure between desired state and current state.
- ```Portable``` - Build reusable modules across an organization.

### Terraform
Terraform is an open source infrastructure as code tool created by HashiCorp that lets you provision Google Cloud resources with declarative configuration files

<img width="600" align="right" src="https://user-images.githubusercontent.com/59575502/197344144-56d2d581-81a5-4949-bd0b-8659660888f5.png">

- Provision resources
- Create resource dependencies
- Standardize configurations
- Validate inputs to resource arguments

##### Terraform features
- Multi-cloud and multi-API
- Open core with enterprise support
- Large community
- Infrastructure provisioning

<img width="1200" src="https://user-images.githubusercontent.com/59575502/197344343-2e4aba29-f71d-4965-870b-1d2dbbfeb09b.png">

### HashiCorp Configuration Language (HCL)
- Terraform's configuration language for creating and managing API-based resources 
- Configuration language, not a programming language.
- Includes limited set of primitives such as variables, resources, outputs and modules. Includes no traditional statements or control loops.

**Syntax**
```
<BLOCK TYPE> "<BLOCK LABEL>" "<BLOCK LABEL>" {
  # Block body 
  <IDENTIFIER> = <EXPRESSION> #Argument
}
```

#### Resources
- Resources are code blocks that define the infrastructure components. Example: Cloud Storage Bucket
- Terraform uses the resource type and the resource name to identify an infrastructure element

#### Providers
- Terraform downloads the provider plugin in the root configuration when the provider is declared.
- Providers expose specific APIs as Terraform resources and manage their interactions.
- Provider configurations belong in the root module of a Terraform configuration. 
- Arguments such as project and region can be declared within the provider block.

#### Variables
- Parameterize resource arguments to eliminate hard coding its values 
**Example:** Region, project ID, zone, etc. 
- Define a resource attribute at run time or centrally in a file with a .tfvars extension.

#### Outputs
- Output values are stored in outputs.tf file.
- Output values expose values of resource attributes.

#### State
- Terraform saves the state of resources it manages in a state file.
- The state file can be stored:
    - Locally (default)
    - Remotely in a shared location 
- You do not modify this file.
- A state is a metadata repository of your infrastructure configuration. 
- A state file is stored by default in a local file named terraform.tfstate. 
- A Terraform state stores the bindings between objects in a remote system and resource instances. 
- The state file records the identity of an instance and updates or deletes in response to configuration changes.

<div align="center">
<img width="700" src="https://user-images.githubusercontent.com/59575502/197346751-ffc9b3c5-56ee-42ea-a5e4-d2e37c8f1298.png">
</div>

#### Modules
A Terraform module is a set of Terraform configuration files in a single directory.
- One or more Terraform configuration files (.tf) in a directory can form a module.
- Modules let you group a set of resources together and reuse them later. 
- The root module consists of the .tf files that are stored in your working directory where you run terraform plan or terraform apply.
-  It is the primary method for code reuse in Terraform. 
-  There are 2 kinds of sources:
    -  ```Local``` - Source within your directory 
    -  ```Remote``` - Source outside your directory
- **USES** - modularize code, eliminate repetition, standardize resources (readable, reusable, abstract, consistent)

```
-- main.tf 
-- providers.tf 
-- variables.tf 
-- outputs.tf

terraform { 
   required_providers { 
       google = {
             source = "hashicorp/google" 
             version = "4.23.0
        }
    }
}
provider "google" {
    # Configuration options 
    project = <project_id> 
    region = "us-central1"
}
resource "resource_type" "resource_name" {
   # Resource-specific arguments
}
```
### Terraform commands
- ```terraform init``` - Initialize the provider with plugin
- ```terraform plan``` - Preview of resources that will be created after terraform apply
- ```terraform apply``` - Create real infrastructure resources
- ```terraform destroy``` - Destroy infrastructure resources
- ```terraform fmt``` - Auto format to match canonical conventions

### Terraform Validator Benefits
- ```Enforce policies``` - Enforce policies at any stage of application development
- ```Remove manual errors``` - Remove manual errors by automating policy validation
- ```Reduce time to learn``` - Reduce learning time by using a single paradigm for all policy management

### Meta-arguments customize the behavior of resources
- ```count``` - Create multiple instances according to the value assigned to the count.
- ```for_each``` - Create multiple resource instances as per a set of strings.
- ```depends_on``` - Specify explicit dependency.
- ```lifecycle``` - Define life cycle of a resource.
- ```provider``` - Select a non-default provider configuration.

### Dependency graph
- Built from the terraform configurations. 
- Interpolates attributes during runtime. 
- Determines the correct order of operations.
- Terraform can handle two kinds of dependencies.
  - ```Implicit dependency``` - Dependencies known to Terraform are detected automatically.
  - ```Explicit dependency``` - Dependencies unknown to Terraform must be configured explicitly.

### The Terraform Registry
• Interactive resource for discovering providers and modules. 
• Solutions developed by HashiCorp, third-party vendors, and the Terraform community.







