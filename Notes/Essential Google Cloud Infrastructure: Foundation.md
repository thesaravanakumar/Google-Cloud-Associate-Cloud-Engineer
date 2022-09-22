## Essential Google Cloud Infrastructure: Foundation

### Virtual Private Cloud
<img width="1200" src="https://user-images.githubusercontent.com/59575502/191574004-3892bf4c-6df8-4010-9190-15dff21945c5.png">
<img width="1200" src="https://user-images.githubusercontent.com/59575502/191574014-f6b074b9-e304-4901-aa6f-f21c0affaa6b.png">

- Every subnet has ```four reserved IP addresses```
- Notice that the **first and second** addresses in the range, .0 and .1, are reserved for the ```network``` and the ```subnet's gateway```, respectively.
- The **second-to-last** address in the range and the **last address**, which are reserved as the ```broadcast``` address.

### IP Address
An ```ephemeral IP``` address is an IP address that doesn't persist beyond the life of the resource. For example, when you create an instance or forwarding rule without specifying an IP address, Google Cloud automatically assigns the resource an ephemeral IP address.

<div align="center">
<img width="600" src="https://user-images.githubusercontent.com/59575502/191576736-d74621d7-134e-4b80-aa2c-e327dfcf7e85.png">
</div>

<img width="1200" src="https://user-images.githubusercontent.com/59575502/191577028-7422d839-aaae-4b41-ac34-f4023006037d.png">

- If you **delete and recreate** an instance, the ```internal IP``` address can change. This change can disrupt connections from other Compute Engine resources, which must obtain the new IP address before they can connect again.
- DNS name always ```points to a specific instance```, no matter what the internal IP address is. Each instance has a ```metadata server``` that also acts as a ```DNS resolver``` for that instance. The metadata server handles all DNS queries for local network resources and routes all other queries to Google's public DNS servers for public name resolution. 
- Instance is not aware of any ```external IP``` address assigned to it. Instead, the network stores a ```lookup table``` that **matches external IP addresses with the internal IP addresses** of the relevant instances.

<div align="center">
<img width="600" src="https://user-images.githubusercontent.com/59575502/191579043-3fedce69-4c7d-49a0-9a0c-af6a96c708f6.png">
</div>

#### CIDR
```Classless Inter-Domain Routing``` -- also known as ```supernetting``` -- is a method of assigning Internet Protocol (IP) addresses that improves the efficiency of address distribution and replaces the previous system based on Class A, Class B and Class C networks.
#### Alias IP Ranges

<img width="500" align="right" src="https://user-images.githubusercontent.com/59575502/191580492-6223a4c4-303c-4dc9-85e2-158fb0c234ce.svg">

> If you have multiple services running on a VM, and you want to assign a different IP address to each service.

All subnets have a primary ```CIDR``` range, which is the range of internal IP addresses that define the subnet. Each VM instance gets its primary internal IP address from this range. You can also allocate alias IP ranges from that primary range, or you can add a secondary range to the subnet and allocate alias IP ranges from the secondary range. Use of alias IP ranges does not require secondary subnet ranges. These secondary subnet ranges merely provide an ```organizational tool```.

- Google publishes the complete list of IP ranges that it announces to the internet in ```goog.json```.
- Google also publishes a list of Google Cloud customer-usable global and regional external IP
addresses ranges in ```cloud.json```.

### Routes and firewall rules
A route is created when a subnet is created. This is what enables VMs on the same network to communicate. 

### [Firewall](https://cloud.google.com/vpc/docs/firewalls)
- Firewall rules let you ```allow or deny``` traffic to and from your VM instances based on a configuration you specify.
- While firewall rules are defined at the ```network level```, connections are allowed or denied on a per-instance basis. You can think of the VPC firewall rules as existing not only between your instances and other networks, but also between individual instances within the same network
- It is ```Global``` like a VPC.
- Existing between instances within same network and instances and other network.
- Each ```VPC``` network acts as a ```distributed firewall``` -> by default it will handle filtering traffic.
> Ex - Applying firewall rules to tagged instances (connections are allowed at per instance basis)

#### Firewall rule is madeup of 4 things,
```
gcloud compute
firewall-rules create
http-allow-rule --
direction=INGRESS --
allow=TCP 22 --
target-tags=red-tag
```
- ```action``` (allow or deny traffic)
- ```direction``` (ingress or egress) -> not both simultaniously
- ```typre of protocol, ports``` (tcp,udp,icmp)
- ```target``` (spource or destination the rule applies)
> Each firewall rule can contain either IPv4 or IPv6 ranges, but not both.

You can apply a firewall rule,
- To all instances in a network
- To a specific instances using tags
- Instances using service accounts
> Only supports ```IPV4``` connections. IPv6 connections are also supported in VPC networks that have IPv6 enabled.
cannot share among networks.

### [Stateful](https://cloud.google.com/vpc/docs/firewalls#specifications)
VPC firewall rules are ```stateful``` -> when a connection is allowed through firewall in either direction, return traffic matching the connection also allowed. You cannot configure a firewall rule to deny associated response traffic.
Return traffic must match the ```5-tuple``` **[source IP, destination IP, source port, destination port, protocol]** of the accepted request traffic, but with the source and destination addresses and ports reversed.

### [Implied rules](https://cloud.google.com/vpc/docs/firewalls#default_firewall_rules)
By default you get implied rules when you create a network.
- Implied allow egress rule
  - 65535 priority
- Implied deny ingress rule
  - 65535 priority
If IPv6 is enabled, the VPC network also has these two implied rules:
- Implied IPv6 allow egress rule.
- Implied IPv6 deny ingress rule

> 65535 is lowest priority so it can be overwrittern.
Google Cloud always allows communication between a VM instance and its corresponding metadata server at ```169.254.169.254```

### [Prepopulated rules](https://cloud.google.com/vpc/docs/firewalls#more_rules_default_vpc)
By default you get prepopulated rules when you create a network.

- ```default-allow-internal``` -> allows all internal traffic
- ```default-allow-ssh``` -> allows ssh internally
- ```default-allow-rdp``` -> connect database internally
- ```default-allow-icmp``` -> ping VMs internally

<div align="center">

[Pricing Docs](https://cloud.google.com/compute/all-pricing#general_network_pricing) | [Pricing Calculator](https://cloud.google.com/products/calculator/)

</div>

### Common network designs
<img width="1200" src="https://user-images.githubusercontent.com/59575502/191584640-76c88b91-d320-4445-8169-3a78438d645c.png">

#### Cloud NAT
> Cloud NAT does not implement inbound NAT.

Cloud NAT is Google's managed network address translation service. It lets you provision your application instances ```without public IP``` addresses while also allowing them to access the Internet in a controlled and efficient manner.

<div align="center">
<img width="600" src="https://user-images.githubusercontent.com/59575502/191584954-3d278870-1118-4f79-8a62-8b7496edda52.png">
</div>


### [Private Google Access](https://cloud.google.com/vpc/docs/private-google-access)

The VPC network has been configured to meet the DNS, routing, and firewall network requirements for Google APIs and services. Private Google Access has been enabled on subnet-a, but not on subnet-b.

- VM A1 can access Google APIs and services, including Cloud Storage, because its network interface is located in subnet-a, which has Private Google Access enabled. Private Google Access applies to the instance because it only has an internal IP address.
- VM B1 cannot access Google APIs and services because it only has an internal IP address and Private Google Access is disabled for subnet-b.
- VM A2 and VM B2 can both access Google APIs and services, including Cloud Storage, because they each have external IP addresses. Private Google Access has no effect on whether or not these instances can access Google APIs and services because both have external IP addresses.

<div align="center">
<img width="600" src="https://user-images.githubusercontent.com/59575502/191585801-0230cb70-3bc6-4be8-9ed2-e75a8281e809.svg">
</div>

---

### [Compute Engine](https://cloud.google.com/compute/docs)
Infrastructure as a service (IaaS)
Predefined or custom machine types:
  - vCPUs (cores) and memory (RAM)
  - Storage
      - Zonal or Regional persistant disk (HDD or SSD)
      - Local SSD
      - Cloud Storage
  - Networking
  - Linux or windows

<img width="1200" src="https://user-images.githubusercontent.com/59575502/191698038-59fd2dc5-5eba-4482-a684-81ea904be6bc.png">

#### VM Access
- Linux VM (SSH)
    - Require firewall rule to allow tcp:22
    - SSH from console or cloud shell via cloud SDK

- Windows VM (RDP)
    - Require firewall rule to allow tcp:3389
    - Require setting the windows password.

#### VM Lifecycle

<img width="1200" src="https://user-images.githubusercontent.com/59575502/191705232-5d34d8b9-db38-44df-aa11-4a0b835b2f9b.png">

<div align="center">

#### [Machine types](https://cloud.google.com/compute/docs/machine-types)


<img width="803" src="https://user-images.githubusercontent.com/59575502/191707597-8df8bedd-76de-4611-a991-315414161856.png">
</div>

### Compute VM Options
#### [Preemptible VMs](https://cloud.google.com/compute/docs/instances/preemptible)
A preemptible VM is an instance that you can create and run at a much lower cost than normal instances.
- Low Price
- Terminate at any time
    - preemptible VM only going to live for up to 24 hours (max)
    - 30-second notification before termination (not garanteed)
- No live migrations nor automatic restarts

#### [Spot VMs](https://cloud.google.com/compute/docs/instances/spot)
Spot VMs are the latest version of preemptible VMs.
- Same price as preemptible
- No minimum or maximum run time
- Spot VMs are finite Compute Engine resources, so they might not always be available.
- No live migrations nor automatic restarts

#### [Sole-Tenant Node](https://cloud.google.com/compute/docs/nodes/sole-tenant-nodes)
A ```sole-tenant node``` is a physical Compute Engine server that is dedicated to hosting VM instances only for your specific project. Use sole-tenant nodes to keep your instances physically separated from instances in other projects, or to group your instances together on the same host hardware.

#### [Shielded VMs](https://cloud.google.com/compute/shielded-vm/docs/shielded-vm)
Shielded VMs offer verifiable integrity to your VM instances, so you can be confident that your instances haven't been compromised by boot or kernel-level malware or rootkits.
- secure boot
- virtual trusted platform modules (vTPM)
- Integrity monitoring

#### [Confidential VMs](https://cloud.google.com/compute/confidential-vm/docs/about-cvm#confidential-vm)
Confidential VMs allows you to encrypt data in use, while it's been processed.
- Easy-to-use without making any code changes or having to compromise performance.
- It is a type of ```N2D Compute Engine VM``` instance running on hosts based on the second generation of AMD Epyc processors, code-named "Rome".
- Compute-heavy workloads, with high memory capacity, high throughput, and support for parallel workloads.

#### What is an image?
- Boot loader
- OS
- File system structure
- Software
- Customizations

### [Disk Options](https://cloud.google.com/compute/docs/disks)
Every single VM comes with a single root persistent disk because you're choosing a base image to have it loaded on. This image is ```bootable``` in that it can attach to VM and boot from it. It is ```durable``` in that it can survive if the VM terminates. To have a boot disk survive a VM deletion, you need to disable the ```Delete boot disk when instance is deleted``` option in the instance properties
- ```Zonal persistent disk``` -> Efficient, reliable block storage.
- ```Regional persistent disk``` -> Regional block storage replicated in two zones.
- ```Local SSD``` -> High performance, transient, local block storage.
- ```Cloud Storage buckets``` -> Affordable object storage.
- ```Filestore``` -> High performance file storage for Google Cloud users.

<div align="center">
  
[Persistent Disk](https://cloud.google.com/compute/docs/disks#pdspecs) | [Local SSDs](https://cloud.google.com/compute/docs/disks#localssds) | [Cloud Storage buckets](https://cloud.google.com/compute/docs/disks#gcsbuckets) | [Firestore](https://cloud.google.com/firestore/docs)
  
 </div>
 
<img width="1200" src="https://user-images.githubusercontent.com/59575502/191743475-9dbaf893-c426-4930-b165-cb1acd0b5ac1.png">
<img width="1200" src="https://user-images.githubusercontent.com/59575502/191743490-d307ccbb-5d23-4dce-a93a-d3ae15873263.png">
<img width="1200" src="https://user-images.githubusercontent.com/59575502/191743496-8887af29-5d8c-42c8-a0d3-dd502b09e378.png">

### Common Compute Engine actions

<img width="600" align="right" src="https://user-images.githubusercontent.com/59575502/191748781-a88a4009-f89c-4845-8935-804209f3d60d.png">

#### Metadata and Scripts
Every VM instance stores its metadata on a ```metadata server```. The metadata server is particularly useful in combination with startup and shutdown scripts because you can use the metadata server to programmatically get unique information about an instance without additional authorization. 

</br>
<img width="600" align="right" src="https://user-images.githubusercontent.com/59575502/191749860-67e1ca0a-2601-41ca-944c-a17ecdc34b3d.png">
</br>

#### Move a VM into new Zone
For geographical reasons or because a zone has been deprecated you can move a VM even if one of these following scenarios apply,
- The VM instance is in a termination stage 
- The VM instance is a shielded VM that uses UEFI's firmware.
To move your VM, you must shut down the VM, move it to its destination zone or region, and then restart it. After you move your VM, update any references that you have pointing to the original resource, such as any target VMs or target pools that point to the earlier VM.

<img width="600" align="right" src="https://user-images.githubusercontent.com/59575502/191762525-0f0f8767-43d5-427b-bd18-b6b6ba8eba73.png">

##### What is snapshots?
- To backup ```critical data``` into a durable storage solution to meet application, availability, and recovery requirements. 
- These are stored in ```Cloud Storage```
- Snapshots can also be used to ```migrate data between zones```.


