## Elastic Google Cloud Infrastructure: Scaling and Automation

### Cloud VPN

- useful for low-volume data connections
- 99.9% SLA (availability)
- supports
  - site-to-site VPN
  - static routes
  - dynamic routes (cloud router)
  - IKEv1 and IKEv2 ciphers (pre-shared)
  - Uses Encapsulated Security Payload (ESP) in tunnel mode with authentication.

[Performance](https://cloud.google.com/network-connectivity/docs/vpn/concepts/overview#network-bandwidth)

* Each VPN has a maximum throughput of ```3Gbps```.
* Maximum transmission unit or ***MTU*** for your on-premises VPN gateway cannot be greater than ```1,460 bytes``` because (small packets = lesser throughput) and for Encapsulating Security Payload (ESP) overhead it should be less than 1460.
* For ingress and egress, the recommended maximum ***packet rate*** for each Cloud VPN tunnel is ```250,000``` (more tunnels = high rate)

There are two types of Cloud VPN gateways: 
- Classic VPN
- HA VPN

#### Classic VPN
- Classic VPN gateways have a single interface, a single external IP address, and support tunnels that use dynamic (BGP) or static routing (policy-based or route-based).
- Classic VPN provides an SLA of 99.9% service availability.
- Classic VPN would be deprecated
- Do not support IPv6

<div align="center">
  
<img width="600" src="https://user-images.githubusercontent.com/59575502/194538441-7eeb2ede-c06a-40d6-bd54-df3095b3b92e.png">


Need an external IPs, tunnels, gateways for a single project. (Total = 2IPs, 2tunnels, 2gateways)
</div>

#### HA VPN
On-premises hosts communicate through one or more IPsec VPN tunnels to Compute Engine virtual machine (VM) instances in your project's Virtual Private Cloud (VPC) networks.

<div align="center">
  
  ![image](https://user-images.githubusercontent.com/59575502/194539392-8beb8ac9-d3e1-4fc7-b918-7c10cc29b096.png)
  
Need 2 external IPs, 2 tunnels, 2 gateways for a single project. (Total = 4 IPs, 4 tunnels, 4 gateways)
</div>

### [Classic VPN vs HA VPN](https://cloud.google.com/network-connectivity/docs/vpn/concepts/overview#comparison_table)
| **Feature**                                                         | **HA VPN**                                                                               | **Classic VPN**                                                                                                                                                                  |
|:-------------------------------------------------------------------:|:----------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| **SLA**                                                             | Provides a 99.99% SLA when configured with two interfaces and two external IP addresses. | Provides a 99.9% SLA.                                                                                                                                                            |
| **Creation of external IP addresses and forwarding rules**          | External IP addresses created from a pool; no forwarding rules required.                 | External IP addresses and forwarding rules must be created.                                                                                                                      |
| **Supported routing options**                                       | Only dynamic routing (BGP).                                                              | Static routing (policy-based, route-based). Dynamic routing is only supported for tunnels that connect to third-party VPN gateway software running on Google Cloud VM instances. |
| **Two tunnels from one Cloud VPN gateway to the same peer gateway** | Supported                                                                                | Not supported                                                                                                                                                                    |
| **API resources**                                                   | Known as the vpn-gateway resource.                                                       | Known as the target-vpn-gateway resource.                                                                                                                                        |
| **IPv6 traffic**                                                    | Supported in Preview (IPv4 and IPv6 configuration)                                                                    | Not supported                                                                                                                                                                    |


### [Active/active and active/passive routing options for HA VPN](https://cloud.google.com/network-connectivity/docs/vpn/concepts/overview#active)
- If a Cloud VPN tunnel goes down, it restarts automatically.
- If an entire virtual VPN device fails, Cloud VPN automatically instantiates a new one with the same configuration.
- The new gateway and tunnel connect automatically.

Depending on the way that you configure route priorities for HA VPN tunnels, you can create an active/active or active/passive routing configuration. For both of these routing configurations, both VPN tunnels remain active.

| **Feature**             | **Active/active**                                                                                                                                                                                                                | **Active/passive**                                                                                                                                                                                                                                                                                                            |
|:-----------------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| **Throughput**          | The effective aggregate throughput is the combined throughput of both tunnels.                                                                                                                                                   | After reducing from two active tunnels to one, the effective overall throughput is cut in half, which can result in slower connectivity or dropped packets.                                                                                                                                                                   |
| **Route advertisement** | Peer gateway advertises the peer network’s routes with ```identical MED``` values for each tunnel. Egress traffic sent to the peer network uses ```equal-cost multipath``` (ECMP) routing.                                                   | Peer gateway advertises the peer network’s routes with ```different MED values``` for each tunnel. Egress traffic sent to the peer network uses the route with the ```highest priority```, as long as the associated tunnel is available. Peer gateway can only use the tunnel with the highest priority to send traffic to Google Cloud. |
| **Failover**            | If one tunnel becomes unavailable, Cloud Router withdraws the learned custom dynamic routes whose next hops are the unavailable tunnel. This withdrawal process can take up to ```40 seconds```, during which packet loss is expected. | Uses a maximum of one tunnel at a time so that the second tunnel is able to handle all your egress bandwidth if the first tunnel fails and needs to be failed over.                                                                                                                                                           |

### Interconnect and Peering
<div align="center">
<img width="600" src="https://user-images.githubusercontent.com/59575502/194542578-58105cec-0c01-4b9a-8947-833db2e57ee7.png">

```Layer two``` connections use a VLAN that pipes directly into your GCP environment, providing connectivity to ```internal IP``` addresses in the RFC 1918 address space. </br>
```Layer three``` connections provide access to G Suite services, YouTube and Google Cloud APIs using ```public IP``` addresses.
  
</div>

### Dedicated Interconnect
Dedicated Interconnect provides direct physical connections between your on-premise network and Google's network. This enables you to transfer large amount of data between networks, which can be more cost-effective than purchasing additional bandwidth over the public Internet.
- Offers a 99.9 percent or a 99.99 percent uptime SLA.

![image](https://user-images.githubusercontent.com/59575502/194543726-81131a58-373a-48c4-a71f-ae37aa684701.png)

### Partner Interconnect
Partner Interconnect provides connectivity between your on-premises network and your VPC network through a supported service provider. This is useful if your data center is in the physical location that cannot reach a Dedicated Interconnect co-location facility or if your data needs don't warrant a Dedicated Interconnect.
- Can be configured to offer a 99.9 percent or a 99.99 percent uptime SLA between Google and the service provider.

<div align="center">
<img width="600" src="https://user-images.githubusercontent.com/59575502/194544189-14609c21-9694-4c5b-93c1-d55e95273b8f.png">
  
  [All colocation facilities](https://cloud.google.com/network-connectivity/docs/interconnect/concepts/choosing-colocation-facilities)   |   [Supported service providers](https://cloud.google.com/network-connectivity/docs/interconnect/concepts/service-providers)
</div>

### Comparison of Interconnect options

<div align="center">
<img width="800" src="https://user-images.githubusercontent.com/59575502/194544734-ef5c77e6-72f0-4bb4-90fa-f4f6a4fa87e3.png">
</div>

### Direct Peering
Direct Peering provides a direct connection between your business network and Google's
- Broad-reaching edge network locations 
- Exchange BGP routes
- Reach all of Google's services
- Peering requirements
- No SLA

GPS edge ```Points of Presence``` or PoPs are where Google's network connects to the rest of the internet via peering. PoPs are present on over 90 Internet exchanges and at over 100 interconnection facilities around the world.

![image (1)](https://user-images.githubusercontent.com/59575502/194545655-42b7e52f-4876-4608-8483-c496ebb207e7.png)

### Carrier Peering
Carrier Peering provides connectivity through a supported partner
- Carrier Peering partner 
- Reach all of Google's services 
- Partner requirements
- No SLA

#### Choosing a connection

<div align="center">
  
| **Interconnect**                                              | **Peering**                                               |
|:-------------------------------------------------------------:|:---------------------------------------------------------:|
| Direct access to ```RFC1918 IP``` addresses in your VPC with an SLA | Access to Google ```public IP``` addresses only without an SLA. |
| Dedicated and partner interconnect, cloud vpn                 | Direct and carrier peering                                |

</div>

<img width="1200" src="https://user-images.githubusercontent.com/59575502/194547157-96af949d-8a21-4cec-90f5-04660d9ab4cc.png">

### [Shared VPC](https://cloud.google.com/vpc/docs/shared-vpc) (software-defined networking on top of Google's [Andromeda](https://cloud.google.com/blog/products/gcp/andromeda-2-1-reduces-gcps-intra-zone-latency-by-40-percent))

Allows an organization to connect resources from multiple projects to a common VPC network, so that they can communicate with each other securely and efficiently using ```internal IPs``` from that network. When you use Shared VPC, you designate a project as a ```host``` project and attach one or more other ```service``` projects to it. The VPC networks in the host project are called Shared VPC networks. Eligible resources from service projects can use ```subnets``` in the Shared VPC network.

* Traffic stays on google's private network and benefits from its security reliability and low latency currently
* GCP lets you expand an existing subnet without affecting any existing VM's IP address, and with ```zero downtime```.
* Organization account is needed.
* ```Compute Engine API``` should be enabled.

> Goal: connect and have centralized control over network resources ( subnets, routes, firewall,..)

<div align="center">

<img width="600" src="https://user-images.githubusercontent.com/59575502/192810342-5dd98ae2-63c2-41f8-bc09-668b322b8f5a.png">
  
Instance A in service project A uses 10.0.1.0/24 subnet in ```us-west-1```. 
Instance B in service project A uses 10.15.2.4/24 subnet in ```us-east-1```. 
Instance A can ping Instace B and vice versa.
  
| **Consideration**      | **Shared VPC** | **VPC Network Peering** |
|:----------------------:|:--------------:|:-----------------------:|
| Across organisation    | No             | Yes                     |
| Within project         | No             | Yes                     |
| Network administration | centralized    | de-centralized          |


</div>

<img width="300" align="right" src="https://user-images.githubusercontent.com/59575502/194573074-8301b6e0-9bac-44ef-8c8f-4ab268e9a8c5.png">

### Managed instance groups
A managed instance group is a collection of ```identical VM``` instances that you control as a single entity using an instance template. 
- Deploy identical instances based on instance template
- Instance group can be resized
- Manager ensures all instances are RUNNING
- Typically used with autoscaler
- Can be a single zone or regional

![image (1)](https://user-images.githubusercontent.com/59575502/194574543-9e84bb0b-48eb-475b-8981-6a151a56ed1c.png)

#### Autoscaling and health checks
##### Autoscaling
- Dynamically add/remove instances:
  - Increases in load
  - Decreases in load
- Autoscaling policy (I you want autoscalling use autoscaling policy)
  - CPU utilization
  - Load balancing capacity
  - Monitoring metrics
  - Queue-based workload

##### Health checks
A health check is very similar to an up time check in stack driver. Define a ```protocol, port and health criteria```. Based on this configuration GCP computes a health state for each instance. 
In health criteria
```Check Interval``` -> how often to check whether an instance is healthy. 
```Time out``` -> How long to wait for a response.
```Healthy threshold``` -> How many successful attempts are decisive.
```Unhealthy threshold``` -> How many failed attempts are decisive.

<div align="center">
<img width="600" alt="Screenshot 2022-10-07 at 7 59 20 PM" src="https://user-images.githubusercontent.com/59575502/194577854-fb2007d5-59ec-47c0-b0de-12f0fbbebe41.png">

"The health check would have to fail twice over a total of 15 seconds before an instance is considered unhealthy"
</div>

### Cloud Load Balancing
Cloud Load Balancing is a fully distributed, software-defined managed service. It is not instance or device-based, so you do not need to manage a physical load balancing infrastructure. 
GCP offers different types of load balancers that can be divided into two categories
- ```Global``` (HTTP/HTTPS, SSL proxy and TCP proxy)
     - Sits in Google's point of presence and are distributed globally
- ```Regional``` (Internal TCP/UDP, Network TCP/UDP and Internal HTTP(S)
     - They distribute traffic to instances that are in a single GCP region. 
     - The _internal_ load balancer uses ```Andromeda```, which is GCP's software-defined network virtualization stack.
     - The _networ_k load balancer uses ```Maglev```, which is a large, distributed software system.

#### HTTP(S) load balancing
HTTPS Load Balancing which acts at ```layer seven``` of the OSI model. This is the application layer which deals with the actual content of each message allowing for routing decisions based on the URL. GCP HTTPS load balancing provides global load balancing for HTTPS requests destined for your instances. This means that your applications are available to your customers at a single ```any-cast IP``` address, which simplifies your DNS setup.
- Uses ```round-robin```

<img width="600" align="right" src="https://user-images.githubusercontent.com/59575502/194579681-72425da7-bd16-4634-90cc-6feb271c9ca8.png">

- Global load balancing 
- Anycast IP address 
- HTTP or port 80 or 8080 
- HTTPs on port 443 
- IPv4 or IPv6 
- Autoscaling 
- URL maps

### HTTP(S) load balancing
- Target HTTP(S) proxy
- One signed SSL certificate installed(minimum)
- Client SSL session terminates at the load balancer
- Support the QUIC transport layer protocol

**Backend Services**
- Health check
- Session affinity (optional) ```attempts to send all requests from the same client to the same VM Instance```
- Time out setting (30-sec default)
- One or more backends
- An instance group (managed or unmanaged)
  - A balancing mode (CPU utilization or RPS)
  - A capacity scaler (ceiling % of CPU/Rate targets)

Example: HTTP Load Balancing, content-based LB

<img width="1200" src="https://user-images.githubusercontent.com/59575502/194584569-c970fa18-9098-4c0b-9b62-cec6c5ad129a.png">

### Network endpoint groups (NEG)
A network endpoint group (NEG) is a configuration object that specifies a group of backend endpoints or services.
There are four types of NEGS:
- Zonal
- Internet
- Serverless
- Hybrid connectivity

## Cloud CDN
Content Delivery Network, uses Google's globally distributed edge points of presence to cache HTTP(S) load-balanced content close to your users. 
#### why should you consider using Cloud CDN?
Cloud CDN caches content at the edge of Google's network providing faster delivery of content to your users while reducing serving costs. You can enable Cloud CDN with a simple checkbox when setting up the backend service of your HTTP(S) load balancer.

<img width="600" align="right" src="https://user-images.githubusercontent.com/59575502/194600141-783d2cc6-3059-410f-abc2-b1b8f0eb37b1.png">

#### But how do you know how Cloud CDN will cache your content? How do you control this?
Cloud CDN cache modes:
- Cache modes control the factors that determine whether or not Cloud CDN caches your content.
- Cloud CDN offers three cache modes:
    - USE_ORIGIN_HEADERS
    - CACHE_ALL_STATIC
    - FORCE_CACHE_ALL

<img width="600" align="right" src="https://user-images.githubusercontent.com/59575502/194604091-c4b8b893-6126-44c5-b08c-864ccd80ed7f.png">

### SSL proxy load balancing
- Global load balancing for encrypted, non-HTTP traffic
- Terminates SSL session at load balancing layer
- IPv4 or IPv6 clients
- Benefits:
    - Intelligent routing
    - Certificate management 
    - Security patching 
    - SSL policies

### TCP proxy load balancing
- Global load balancing for unencrypted, non-HTTP traffic
- Terminates TCP sessions at load balancing layer
- IPv4 or IPv6 clients
- Benefits:
    - Intelligent routing
    - Security patching

### Network load balancing
- Regional, non-proxied load balancer
- Forwarding rules (IP protocol data)
- Traffic
    - UDP
    - TCP/SSL ports
- Architecture: 
    - Backend service-based
    - Target pool-based

![image](https://user-images.githubusercontent.com/59575502/194605696-ea4fd55d-31ff-4f77-bc03-9bc74b6d221b.png)

### Internal load balancing
Internal TCP/UDP load balancing
- Regional, private load balancing
    - VM instances in same region
    - RFC 1918 IP addresses
- TCP/UDP traffic
- Reduced latency, simpler configuration
- Software-defined, fully distributed load balancing

#### Internal HTTP(S) load balancing
- Regional, private load balancing
    - VM instances in same region
    - RFC 1918 IP addresses
- HTTP, HTTPS, or HTTP/2 protocols
- Based on open source Envoy proxy ```enables rich traffic control based on HTTPS parameters```

![image](https://user-images.githubusercontent.com/59575502/194610457-dc4f482c-4658-436a-abff-6bbdfffb0f1d.png)

### Choosing a load balancer
<img width="1200" src="https://user-images.githubusercontent.com/59575502/194614504-af2c92cc-bd26-4718-ae27-95f13159f8fe.png">

| **Load balancer** | **Traffic type**                                              | **Global/ Regional** | **External/ Internal** | **External ports for load balancing**                           |
|:-----------------:|:-------------------------------------------------------------:|:--------------------:|:----------------------:|:---------------------------------------------------------------:|
| HTTP(S)           | HTTP or HTTPS                                                 | Global IPv4          | External               | HTTP on 80 or 8080; HTTPS on 443                                |
| SSL Proxy         | TCP with SSL offload                                          | IPv6                 |                        | 25, 43, 110, 143, 195, 443, 465, 587, 700, 993, 995, 1883, 5222 |
| TCP Proxy         | TCP without SSL offload Does not preserve client IP addresses |                      |                        | 25, 43, 110, 143, 195, 443, 465, 587, 700, 993, 995, 1883, 5222 |
| Network TCP/UDP   | TCP/UDP without SSL offload Preserves client IP addresses     | Regional IPv4        |                        | Any                                                             |
| Internal TCP/UDP  | TCP or UDP                                                    |                      | Internal               | Any                                                             |
| Internal HTTP(S)  | HTTP or HTTPS                                                 |                      |                        | HTTP on 80 or 8080; HTTPS on 443                                |

---

### IAC 

#### Infrastructure as code (laC) allows quick provisioning and removing of infrastructures
- Build an infrastructure when needed.
- Destroy the infrastructure when not in use.
- Create identical infrastructures for dev, test, and prod.
- Can be part of a CI/CD pipeline.
- Templates are the building blocks for disaster recovery procedures.
- Manage resource dependencies and complexity.
- Google Cloud supports many lac tools.

### Terraform
Terraform is an infrastructure automation tool
- Repeatable deployment process
- Declarative language
- Focus on the application
- Parallel deployment 
- Template-driven

> considered as a first class tool in Google Cloud. Already installed in cloud shell

#### Deploying Infrastructure with Terraform
- terraform init
- terraform plan
- terraform apply

### Google Cloud Marketplace
- Deploy production-grade solutions
- Single bill for Google Cloud and third-party services
- Manage solutions using Terraform
- Notifications when a security update is available
- Direct access to partner support

### Managed Service
#### BigQuery
BigQuery is Google Cloud's serverless, highly scalable, and cost-effective cloud data warehouse
- Fully managed
- Petabyte scale
- SQL interface
- Very fast

#### Dataflow
Use Cloud Dataflow to execute a wide variety of data processing patterns
- Serverless, fully managed data processing
- Batch and stream processing with autoscale
- Open source programming using 3 beam
- Intelligently scale to millions of QPS

#### Dataprep
Use Cloud Dataprep to visually explore, clean, and prepare data for analysis and machine learning
- Serverless, works at any scale
- Suggests ideal data transformation
- Focus on data analysis
- Integrated partner service operated by Trifacta

#### Dataproc
Cloud Dataproc is a service for running Apache Spark and Apache Hadoop clusters
- Low cost (per-second, preemptible)
- Super fast to start, scale, and shut down
- Integrated with GCP
- Managed service
- Simple and familiar
