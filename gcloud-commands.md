## Basic Commands
#### Ping (mynetwork-allow-icmp)
Ping stands for ```Packet Internet Groper```. It uses the ```ICMP``` (Internet Control Message Protocol) to send an echo request message. If the listening server can answer it sends an echo message back, displaying information to the user.
</br>
Ping timeout ```ping -c 3 google.com```

#### SSH (mynetwork-allow-ssh)
The Secure Shell Protocol is a cryptographic network protocol for operating network services securely over an unsecured network. ```tcp:22```

#### Cloud shell provides the following:

- Temporary Compute Engine VM
- Command-line access to the instance via a browser
- 5 GB of persistent disk storage ($HOME dir)
- Pre-installed Cloud SDK and other tools
- ```gcloud``` for working with Compute Engine and many Google Cloud services
- ```gsutil``` for working with Cloud Storage
- ```kubectl``` for working with Google Kubernetes Engine and Kubernetes
- ```bq``` for working with BigQuery
- Language support for Java, Go, Python, Node.js, PHP, and Ruby
- Web preview functionality
- Built-in authorization for access to resources and instances

### CLoud Strorage Bucket
</br>

```gsutil mb gs://<BUCKET_NAME>``` -> make bucket
</br>

```gsutil mb -l $LOCATION gs://$DEVSHELL_PROJECT_ID``` -> bucket named after your project ID


Copy the file uploaded into Cloud Shell temp VM to bucket you created.
```gsutil cp [MY_FILE] gs://[BUCKET_NAME]```

Retrieve a banner image from a publicly accessible Cloud Storage location:
</br>
```gsutil cp gs://cloud-training/gcpfci/my-excellent-blog.png my-excellent-blog.png```

Copy the banner image to your newly created Cloud Storage bucket:
</br>
```gsutil cp my-excellent-blog.png gs://$DEVSHELL_PROJECT_ID/my-excellent-blog.png```

Modify the Access Control List of the object you just created so that it is readable by everyone:
</br>
```gsutil acl ch -u allUsers:R gs://$DEVSHELL_PROJECT_ID/my-excellent-blog.png```


### VPC 
To list the available VPC networks
</br>
```gcloud compute networks list```

To list the available VPC subnets (sorted by VPC network)
</br>
```gcloud compute networks subnets list --sort-by=NETWORK```

To create the VPC network,
</br>
```gcloud compute networks create [VPC_NAME] --subnet-mode=custom```

To create the [VPC_NAME] subnet
</br>
```gcloud compute networks subnets create [SUBNET_NAME] --network=[VPC_NAME] --region=us-central1 --range=172.16.0.0/24```

To create the [VPC_NAME] to allow-icmp-ssh-rdp firewall rule
</br>
```gcloud compute firewall-rules create [VPC_NAME] --direction=INGRESS --priority=1000 --network=privatenet --action=ALLOW --rules=icmp,tcp:22,tcp:3389 --source-ranges=0.0.0.0/0```

To list all the firewall rules (sorted by VPC network)
</br>
```gcloud compute firewall-rules list --sort-by=NETWORK```

To create the VM instance
</br>
```gcloud compute instances create [VM_NAME] --zone=us-central1-c --machine-type=f1-micro --subnet=[SUBNET_NAME] --image-family=debian-10 --image-project=debian-cloud --boot-disk-size=10GB --boot-disk-type=pd-standard --boot-disk-device-name=privatenet-us-vm```

To list all the VM instances (sorted by zone)
</br>
```gcloud compute instances list --sort-by=ZONE```

To see information about unused and used memory and swap space on your custom VM
```free```

To see details about the RAM installed on your VM
```sudo dmidecode -t 17```

To verify the number of processors
```nproc```

To see details about the CPUs installed on your VM
```lscpu```


## GCLOUD BASICS
```
# Init of the tool
gcloud init

# Gcloud structure
$ gcloud compute instances  list
# |------base--| |--who--| |-what-|

$ gcloud components install  kubectl # exception
# |------base-----| |-what-| |-who-|

# Set the project
gcloud config set project PROJECT-NAME

# Bucket Versioning (NB: is gsutil)
gsutil versioning set (on|off) gs://<bucket_name>...
gsutil versioning get gs://<bucket_name>...

# List VM
gcloud compute instances list [--zones] [--format json]

# Create VM with boot disk
gcloud compute instances create VM_NAME \
    --source-snapshot=BOOT_SNAPSHOT_NAME \
    --boot-disk-size=BOOT_DISK_SIZE \
    --boot-disk-type=BOOT_DISK_TYPE \
    --boot-disk-device-name=BOOT_DISK_NAME

# Install components (e.g. kubectl, minikube, kustomize, bq)
gcloud components list
gcloud components install PRODUCT

# Set a default Region
gcloud config set compute/region europe-west1

# Create Compute Engine persistent disks
gcloud compute disks create my-disk-1 my-disk-2 --zone=us-east1-a

# Resize a cluster nodes
gcloud container clusters resize sample-cluster --num-nodes=2

# Add IAM policy binding
gcloud projects add-iam-policy-binding example-project-id-1  --member='user:test-user@gmail.com' --role='roles/editor'

# Delete `default` VPC (NB: start with 'compute')
gcloud compute networks delete defaulta

# Create VPC
gcloud compute networks create

# gcloud Wide Flags
--account         # GCP user account to use for invocation
--project         # The Google Cloud Platform project ID to use for this invocation
--billing-project # project that will be charged quota for operations performed
--configuration   # The configuration to use for this command invocation
--flags-file      # A YAML or JSON file that specifies a --flag:value dictionary
--flatten         # Use to "flatten" resources list
--format          # Set the format for printing command output resources
--log-http        # Log all HTTP server requests and responses to stderr
--trace-token     # Token used to route traces of service requests for investigation of issues
--verbosity
--quiet
--impersonate-service-account

# List VPC networks
gcloud compute networks list

# List existing clusters for running containers
gcloud container clusters list

# Describe cluster image info (NB: is gcloud not kubectl)
gcloud container images describe gcr.io/myproject/myimage:tag
```
