## Basic Commands
#### Ping (mynetwork-allow-icmp)
Ping stands for ```Packet Internet Groper```. It uses the ```ICMP``` (Internet Control Message Protocol) to send an echo request message. If the listening server can answer it sends an echo message back, displaying information to the user.
</br>
Ping timeout ```ping -c 3 google.com```

#### SSH (mynetwork-allow-ssh)
The Secure Shell Protocol is a cryptographic network protocol for operating network services securely over an unsecured network. ```tcp:22```


For convenience, enter your chosen location into an environment variable called LOCATION. Enter one of these commands:

export LOCATION=US
In Cloud Shell, the DEVSHELL_PROJECT_ID environment variable contains your project ID. Enter this command to make a bucket named after your project ID:
gsutil mb -l $LOCATION gs://$DEVSHELL_PROJECT_ID
Retrieve a banner image from a publicly accessible Cloud Storage location:
gsutil cp gs://cloud-training/gcpfci/my-excellent-blog.png my-excellent-blog.png
Copy the banner image to your newly created Cloud Storage bucket:

gsutil cp my-excellent-blog.png gs://$DEVSHELL_PROJECT_ID/my-excellent-blog.png
Modify the Access Control List of the object you just created so that it is readable by everyone:
gsutil acl ch -u allUsers:R gs://$DEVSHELL_PROJECT_ID/my-excellent-blog.png
