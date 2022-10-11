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

## Getting started
Get going with the gcloud CLI.
- [gcloud init](https://cloud.google.com/sdk/gcloud/reference/init): Initialize, authorize, and configure the gcloud CLI.
- [gcloud version](https://cloud.google.com/sdk/gcloud/reference/version): Display version and installed components.
- [gcloud components install](https://cloud.google.com/sdk/gcloud/reference/components/install): Install specific components.
- [gcloud components update](https://cloud.google.com/sdk/gcloud/reference/components/update): Update your gcloud CLI to the latest version.
- [gcloud config set project](https://cloud.google.com/sdk/gcloud/reference/config/set): Set a default Google Cloud project to work on.
- [gcloud info](https://cloud.google.com/sdk/gcloud/reference/info): Display current gcloud CLI environment details.

### Help
gcloud CLI is happy to help.

- [gcloud help](https://cloud.google.com/sdk/gcloud/reference/help): Search the gcloud CLI reference documents for specific terms.
- [gcloud feedback](https://cloud.google.com/sdk/gcloud/reference/feedback): Provide feedback to the gcloud CLI team.
- [gcloud topic](https://cloud.google.com/sdk/gcloud/reference/topic): Supplementary help material for non-command topics like accessibility, filtering, and formatting.

### Personalization
Make the gcloud CLI your own; personalize your configuration with properties.

- [gcloud config set](https://cloud.google.com/sdk/gcloud/reference/config/set): Define a property (like compute/zone) for the current configuration.
- [gcloud config get-value](): Fetch the value of a gcloud CLI property.
- [gcloud config list](https://cloud.google.com/sdk/gcloud/reference/config/list): Display all the properties for the current configuration.
- [gcloud config configurations create](https://cloud.google.com/sdk/gcloud/reference/config/configurations/create): Create a new named configuration.
- [gcloud config configurations list](https://cloud.google.com/sdk/gcloud/reference/config/configurations/list): Display a list of all available configurations.
- [gcloud config configurations activate](https://cloud.google.com/sdk/gcloud/reference/config/configurations/activate): Switch to an existing named configuration.

### Authorization and Credentials
Grant and revoke authorization to the gcloud CLI and manage credentials.

- [gcloud auth login](https://cloud.google.com/sdk/gcloud/reference/auth/login): Authorize Google Cloud access for the gcloud CLI with Google Cloud user credentials and set the current account as active.
- [gcloud auth activate-service-account](https://cloud.google.com/sdk/gcloud/reference/auth/activate-service-account): Authorize Google Cloud access similar to gcloud auth login but with service account credentials.
- [gcloud auth application-default](https://cloud.google.com/sdk/gcloud/reference/auth/application-default): Manage your Application Default Credentials (ADC) for Cloud Client Libraries.
- [gcloud auth list](https://cloud.google.com/sdk/gcloud/reference/auth/list): List all credentialed accounts.
- [gcloud auth print-access-token](https://cloud.google.com/sdk/gcloud/reference/auth/print-access-token): Display the current account's access token.
- [gcloud auth revoke](https://cloud.google.com/sdk/gcloud/reference/auth/revoke): Remove access credentials for an account.

### Projects
Manage project access policies.

- [gcloud projects describe](https://cloud.google.com/sdk/gcloud/reference/projects/describe): Display metadata for a project (including its ID).
- [gcloud projects add-iam-policy-binding](https://cloud.google.com/sdk/gcloud/reference/projects/add-iam-policy-binding): Add an IAM policy binding to a specified project.

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

    
| **Name**                 | **Summary**                                                          |
|:------------------------:|:--------------------------------------------------------------------:|
| Check version & settings | ```gcloud version```, ```gcloud info```, ```gcloud components list```                  |
| Init profile             | ```gcloud init``` This will ask you to open an OpenID URL                  |
| List all zones           | ```gcloud compute zones list```                                            |
| Upgrade local SDK        | ```gcloud components update```, ```gcloud components update --version 219.0.1``` |

### BUCKET BASIC

| **Name**                   | **Summary**                                                              |
|:--------------------------:|:------------------------------------------------------------------------:|
| List all buckets and files | ```gsutil ls, gsutil ls -lh gs://<bucket-name>```                            |
| Download file              | ```gsutil cp gs://<bucket-name>/<dir-path>/package-1.1.tgz .```                |
| Upload file                | ```gsutil cp <filename> gs://<bucket-name>/<directory>/```                     |
| Cat file                   | ```gsutil cat gs://<bucket-name>/<filepath>/```                                |
| Delete file                | ```gsutil rm gs://<bucket-name>/<filepath>```                                  |
| Move file                  | ```gsutil mv <src-filepath> gs://<bucket-name>/<directory>/<dest-filepath>```  |
| Copy folder                | ```gsutil cp -r ./conf gs://<bucket-name>/```                                  |
| Show disk usage            | ```gsutil du -h gs://<bucket-name/<directory>```                               |
| Create bucket              | ```gsutil mb gs://<bucket-name>```                                             |
| Caculate file sha1sum      | ```gsha1sum syslog-migration-10.0.2.tgz, shasum syslog-migration-10.0.2.tgz``` |
| Gsutil help                | ```gsutil help```, gsutil help cp, gsutil help options                         |

### GCP PROJECT   
| **Name**          | **Summary**                                    |
|:-----------------:|:----------------------------------------------:|
| List projects     | ```gcloud config list```, ```gcloud config list project``` |
| Show project info | ```gcloud compute project-info describe```           |
| Switch project    | ```gcloud config set project <project-id>```         |
| List service available | ```gcloud services list --available```       |
| Enable services | ```gcloud services enable container.googleapis.com``` |
    
### GKE    
| **Name**                                | **Summary**                                              |
|:---------------------------------------:|:--------------------------------------------------------:|
| Display a list of credentialed accounts | ```gcloud auth list```                                         |
| Set the active account                  | ```gcloud config set account <ACCOUNT>```                      |
| Set kubectl context                     | ```gcloud container clusters get-credentials <cluster-name>``` |
| Change region                           | ```gcloud config set compute/region us-west```                 |
| Change zone                             | ```gcloud config set compute/zone us-west1-b```                |
| List all container clusters             | ```gcloud container clusters list```                           |
    
### IAM
| **Name**                                | **Summary**                                                     |
|:---------------------------------------:|:---------------------------------------------------------------:|
| Authenticate client                     | ```gcloud auth activate-service-account --key-file <key-file>```      |
| Display a list of credentialed accounts | ```gcloud auth list```                                                |
| To authenticate with a user identity.   | ```gcloud auth login```                                                |
| Set the active account                  | ```gcloud config set account <ACCOUNT>```                             |
| Auth to GCP Container Registry          | ```gcloud auth configure-docker```                                    |
| Print token for active account          | ```gcloud auth print-access-token```, ```gcloud auth print-refresh-token``` |
| Revoke previous generated credential    | ```gcloud auth <application-default> revoke```                        |

### BUCKET SECURITY
| **Name**                | **Summary**                                                                         |
|:-----------------------:|:-----------------------------------------------------------------------------------:|
| Make all files readable | ```gsutil -m acl set -R -a public-read gs://<bucket-name>/```                             |
| Config auth             | ```gsutil config -a```                                                                    |
| Grant bucket access     | ```gsutil iam ch user:denny@gmail.com:objectCreator,objectViewer gs://<bucket-name>```    |
| Remove bucket access    | ```gsutil iam ch -d user:denny@gmail.com:objectCreator,objectViewer gs://<bucket-name>``` |

### VM
| **Name**           | **Summary**                                                                                             |
|:------------------:|:-------------------------------------------------------------------------------------------------------:|
| List all instances | ```gcloud compute instances list, gcloud compute instance-templates list```                                   |
| Show instance info | ```gcloud compute instances describe "<instance-name>" --project "<project-name>" --zone "us-west2-a"```      |
| Stop an instance   | ```gcloud compute instances stop instance-2```                                                                |
| Start an instance  | ```gcloud compute instances start instance-2```                                                               |
| Create an instance | ```gcloud compute instances create vm1 --image image-1 --tags test --zone "<zone>" --machine-type f1-micro``` |
| SSH to instance    | ```gcloud compute ssh --project "<project-name>" --zone "<zone-name>" "<instance-name>"```                    |
| Download files     | ```gcloud compute copy-files example-instance:~/REMOTE-DIR ~/LOCAL-DIR --zone us-central1-a```                |
| Upload files       | ```gcloud compute copy-files ~/LOCAL-FILE-1 example-instance:~/REMOTE-DIR --zone us-central1-a```             |

### DISKS & VOLUMES
| **Name**            | **Summary**                                                                  |
|:-------------------:|:----------------------------------------------------------------------------:|
| List all disks      | ```gcloud compute disks list```                                                    |
| List all disk types | ```gcloud compute disk-types list```                                               |
| List all snapshots  | ```gcloud compute snapshots list```                                                |
| Create snapshot     | ```gcloud compute disks snapshot <diskname> --snapshotname <name1> --zone $zone``` |

### NETWORK    
| **Name**              | **Summary**                                                                       |
|:---------------------:|:---------------------------------------------------------------------------------:|
| List all networks     | ```gcloud compute networks list```                                                      |
| Detail of one network | ```gcloud compute networks describe <network-name> --format json```                     |
| Create network        | ```gcloud compute networks create <network-name>```                                     |
| Create subnet         | ```gcloud compute networks subnets create subnet1 --network net1 --range 10.5.4.0/24``` |
| Get a static ip       | ```gcloud compute addresses create --region us-west2-a vpn-1-static-ip```               |
| List all ip addresses | ```gcloud compute addresses list```                                                     |
| Describe ip address   | ```gcloud compute addresses describe <ip-name> --region us-central1```                  |
| List all routes       | ```gcloud compute routes list```                                                        |
| Generate ssh config   | ```gcloud compute config-ssh```                                                         |
| Windows RDP reset windows password| ```gcloud compute reset-windows-password instance --user=jdoe```            |

### DNS
| **Name**                          | **Summary**                                           |
|:---------------------------------:|:-----------------------------------------------------:|
| List of all record-sets in myzone | ```gcloud dns record-sets list --zone my_zone```            |
| List first 10 DNS records         | ```gcloud dns record-sets list --zone my_zone --limit=10``` |
    
### FIREWALL
| **Name**                   | **Summary**                                                                              |
|:--------------------------:|:----------------------------------------------------------------------------------------:|
| List all firewall rules    | ```gcloud compute firewall-rules list```                                                       |
| List all forwarding rules  | ```gcloud compute forwarding-rules list```                                                     |
| Describe one firewall rule | ```gcloud compute firewall-rules describe <rule-name>```                                       |
| Create one firewall rule   | ```gcloud compute firewall-rules create my-rule --network default --allow tcp:9200 tcp:3306``` |
| Update one firewall rule   | ```gcloud compute firewall-rules update default --network default --allow tcp:9200 tcp:9300``` |

### IMAGES & CONTAINERS    
| **Name**                    | **Summary**                                              |
|:---------------------------:|:--------------------------------------------------------:|
| List all images             | ```gcloud compute images list```                               |
| List all container clusters | ```gcloud container clusters list```                           |
| Set kubectl context         | ```gcloud container clusters get-credentials <cluster-name>``` |

### RDS    
| **Name**                    | **Summary**                                              |
|:---------------------------:|:--------------------------------------------------------:|
| List all sql instances      | ```gcloud sql instances list```                                |    
    
### SERVICES    
| **Name**                           | **Summary**                            |
|:----------------------------------:|:--------------------------------------:|
| List my backend services           | ```gcloud compute backend-services list```   |
| List all my health check endpoints | ```gcloud compute http-health-checks list``` |
| List all URL maps                  | ```gcloud compute url-maps list```           |
    
We can impersonate service account from a user or another service account, a short-lived token is used instead of service account key.
```
# serviceAccount:ansible  impersonate as a svc account terraform@${PROJECT_ID}.iam.gserviceaccount.com
# ${SA_PROJECT_ID} is the global project storing all the service accounts
TF_SA_EMAIL=terraform@${SA_PROJECT_ID}.iam.gserviceaccount.com
ANSIBLE_SA_EMAIL="ansible@${SA_PROJECT_ID}.iam.gserviceaccount.com"
gcloud iam service-accounts add-iam-policy-binding ${TF_SA_EMAIL} \
    --project ${SA_PROJECT_ID} \
    --member "serviceAccount:$ANSIBLE_SA_EMAIL" \
    --role roles/iam.serviceAccountTokenCreator
# create a gcp project $A_PROJECT_ID under $A_FOLDER_ID
gcloud projects --impersonate-service-account=$TF_SA_EMAIL create $A_PROJECT_ID --name=$A_PROJECT_NAME --folder=$A_FOLDER_ID
```
```
# user:pythonrocks@gmail.com impersonate as a svc account terraform@${PROJECT_ID}.iam.gserviceaccount.com
TF_SA_EMAIL=terraform@your-service-account-project.iam.gserviceaccount.com
gcloud iam service-accounts add-iam-policy-binding  $TF_SA_EMAIL --member=user:pythonrocks@gmail.com \
--role roles/iam.serviceAccountTokenCreator

gcloud container clusters list --impersonate-service-account=terraform@${PROJECT_ID}.iam.gserviceaccount.com    
```    

### Cloud Build
```
# user defined
gcloud builds submit --config=cloudbuild.yaml --substitutions=_BRANCH_NAME=foo,_BUILD_NUMBER=1 .

# override built in TAG_NAME
gcloud builds submit --config=cloudbuild.yaml --substitutions=TAG_NAME=v1.0.1

# cloud build with artifact registry
export GCP_REGION="us-east1"
export TEST_IMAGE="us-docker.pkg.dev/google-samples/containers/gke/hello-app:1.0"
export IMAGE_NAME="hello-app"
export REPO_NAME=team1
export TAG_NAME="tag1"
docker pull $TEST_IMAGE
docker tag $TEST_IMAGE \
    ${GCP_REGION}-docker.pkg.dev/${PROJECT_ID}/${REPO_NAME}/${IMAGE_NAME}:${TAG_NAME}
docker push ${GCP_REGION}-docker.pkg.dev/${PROJECT_ID}/${REPO_NAME}/${IMAGE_NAME}:${TAG_NAME}
# build / push image to artifact registry (using local Dockerfile)
gcloud builds submit --tag ${GCP_REGION}-docker.pkg.dev/${PROJECT_ID}/${REPO_NAME}/${IMAGE_NAME}:${TAG}
```    
    
### Private Service Access
Useful for services like Cloud SQL and Redis, peering between a custom VPC to a managed VPC by google.
```
gcloud services vpc-peerings list --network=my-vpc
```

### Shared vpc
```
# Enable shared-vpc in '${NETWORK_PROJECT_ID}'
gcloud services enable --project ${NETWORK_PROJECT_ID} compute.googleapis.com
gcloud compute shared-vpc enable ${NETWORK_PROJECT_ID}

# Associate a service project with '${NETWORK_PROJECT_ID}'
gcloud services enable --project ${PLATFORM_PROJECT_ID} compute.googleapis.com
gcloud compute firewall-rules delete --project ${PLATFORM_PROJECT_ID} --quiet default-allow-icmp default-allow-internal default-allow-rdp default-allow-ssh
gcloud compute networks delete --project ${PLATFORM_PROJECT_ID} --quiet default
gcloud compute shared-vpc associated-projects add ${PLATFORM_PROJECT_ID} --host-project ${NETWORK_PROJECT_ID}

## Disassociate a service project from host project.
gcloud compute shared-vpc associated-projects remove ${PLATFORM_PROJECT_ID} --host-project ${NETWORK_PROJECT_ID}
```

### Interconnect
```
# list Google Compute Engine interconnect locations
gcloud compute interconnects locations list    
```    

### Cloud Run
```
# deploy a service on Cloud Run in us-central1 and allow unauthenticated user
gcloud run deploy --image gcr.io/${PROJECT-ID}/helloworld --platform managed --region us-central1 --allow-unauthenticated

# list services
gcloud run services list
# get endpoint url for a service
gcloud run services describe <service_name> --format="get(status.url)"

export SA_NAME="cloud-scheduler-runner"
export SA_EMAIL="${SA_NAME}@${PROJECT_ID}.iam.gserviceaccount.com"

# create service account
gcloud iam service-accounts create $SA_NAME \
    --display-name "${SA_NAME}"

# add sa binding to cloud run app
gcloud run services add-iam-policy-binding $APP_DIR \
    --platform managed \
    --region $GCP_REGION \
    --member=serviceAccount:$SA_EMAIL \
    --role=roles/run.invoker
# fetch the service URL
export APP="helloworld"
export SVC_URL=$(gcloud run services describe $APP --platform managed --region $GCP_REGION --format="value(status.url)")

# create the job to hit URL every 1 minute
gcloud scheduler jobs create http test-job --schedule "*/1 * * * *" \
    --http-method=GET \
    --uri=$SVC_URL \
    --oidc-service-account-email=$SA_EMAIL \
    --oidc-token-audience=$SVC_URL

export GCP_REGION="us-east1" 
export SERVICE_NAME="hello-service"
# deploy app to Cloud Run
gcloud run deploy $SERVICE_NAME \
    --platform managed \
    --region $GCP_REGION \
    --allow-unauthenticated \
    --image ${GCP_REGION}-docker.pkg.dev/${PROJECT_ID}/${REPO_NAME}/${IMAGE_NAME}:${TAG_NAME}

# confirm service is running
gcloud run services list \
    --platform managed \
    --region $GCP_REGION
# test URL
export SVC_URL=$(gcloud run services describe $SERVICE_NAME --platform managed --region $GCP_REGION --format="value(status.url)")

curl -X GET $SVC_URL
# Hello, world!
# Version: 1.0.0
# Hostname: localhost
```

### Artifact registry
```
export REPO_NAME=team1
export GCP_REGION="us-east1" 

gcloud artifacts repositories create $REPO_NAME \
    --repository-format=docker \
    --location=$GCP_REGION \
    --description="Docker repository"

# Configure auth
gcloud auth configure-docker ${GCP_REGION}-docker.pkg.dev
```
