---
title: Virtual Machines and Networks
date: April 13, 2026 11:17 AM
categories:
  - cloud-computing
tags:
  - gcp
  - virtual-machines
  - networking
  - google-cloud
description: "This is part 2 of my notes for the course: Google Cloud
  Fundamentals: Core Infrastructure."
toc: true
comments: true
math: false
image: false
---
# Virtual Private Cloud (VPC)
A VPC is a secure, private network hosted within a public cloud.

Google VPC networks are global and can have subnets in any Google Cloud region worldwide.

Think of it as a logical network layer that can span globally to connect all of your computing resources. You can create subnets to group resources based on your needs and security concerns.

Google by default provides subnets for each regions. These networks are not suitable for production because they have very board network policy.

So, to be secure you would need to create your own **VPC**. You can add resources from different zones and regions into your subnet. This capability let you create solutions that span multiple regions but retains a simple network layout.

# Compute Engine
This solution lets users create and run virtual machines on google infrastructure.

Each VM has full capacity as a full-fledged operating system.

You can run Windows/Linux or even bring your own operating systems.

Google provides Cloud Marketplace where you find templates of software solutions so you can easily deploy your own version.

When you are using Compute Engine, you only pay for what you use. That means you can custom a machine configuration to match your need. For example you can choose a CPU-centric or memory-centric depending on your workload. This reduces wasting money on resources you won't need.

Google offers various discounts for Compute Engine. Consider those to save money:
- Sustained-use
- Committed-use
- Preemptible & Spot VM: Compute Engine can terminate your job if resource is needed elsewhere. **Make sure your job can be stopped and restarted safely**.

Compute Engine offers **several types of storage solutions**:
- Zonal Disk
- Regional Disk
- Object Storage Buckets
- Local SSD
- Firestore

These solutions offer different performance characteristics and have unique price. 

# Scaling virtual machines

There are two ways to scale your software solution:
- **Horizontal scaling**: adding more machines that run the same applications. Google offers **Autoscaling** for this. You can create *Instance Group* and define minimum - maximum number of instances in a group.

- **Vertical scaling**: giving a machine more computing (CPU) and memory resources to handle bigger tasks. This is only suitable for non-parallelizable workloads.

# Important VPC capabilities
## Built-in - Things that you do not need to provide
- Routing: provided using route tables.
- Firewall: you can define rules through network tags on Compute Engine instances.

## Peering and Sharing
You can connect different VPC using **Peering**. 

You can also create a **Shared VPC** to have multiple Cloud Identities to interact with that  VPC. 

# Cloud Load Balancing
Cloud Load Balancing is a **service** you can put in front of your traffic.

The service itself is fully distributed, software-defined and managed service by Google.

Cloud Load Balancing provides automatic region failover and handles sudden traffic spikes by itself.

There are different kinds of load balancer you can use based on your need:
- Application Load Balancer (HTTP/HTTPS)
- Network Load Balancer (TCP/UDP/Other): Either Proxy or Passthrough balancers.

**Proxy Balancers** will terminate client connections and establishing new ones to backend services.

**Passthrough Balancers** will **NOT** terminate client connections. They direct the connections to the backend instead.

# Cloud Domain Name Service (DNS)
Google offers **Cloud DNS** as a managed DNS service. You can publish your DNS information and have them served from redundant locations around the world.

# Cloud Content Delivery Network (CDN)
## Edge Caching
This is the technique of keeping copies of your content close to your users. So multiple users in a close proximity can benefit from a single cached copy of data.
## Cloud CDN
You can enable Google's Cloud CDN with a single checkbox if you are using *Application Load Balancer*.

# Connecting networks to Google VPC
Read more: [Google's Document on Choosing Network Solution](https://docs.cloud.google.com/network-connectivity/docs/how-to/choose-product#connecting-sites-using-google-cloud)
## Cloud VPN
This option creates a *tunnel* connection to the VPC. This is done over the Internet so it can be unsecure.

## Direct Peering
This option means putting a router inside your public datacenter to act as a Google Point of Presence (PoP).
This is useful if your network needs to access Google public services. For example, you run your machines on-premise and you want them connected to BigQuery without going through the internet.

## Carrier Peering
You can contract with a Google's partner to get connected to Google Cloud through a service provider's network. This is **NOT** covered by *Google Service Level Agreement*.

## Dedicated Interconnect
This option allows one or more private connections to Google. It provides the *highest uptimes* and high *SLA*. You can utilize a VPN for even greater reliability.
Basically means bypassing the Internet and daisy-chain your data center to Google's server.

## Partner Interconnect
Interconnect through a supported service provider. This is useful if the customer's data center can not reach a Dedicated Interconnect facility or if the customer does not need the full 10Gbps bandwidth.
## Cross-cloud Interconnect
Privately connect VPCs across different cloud service provider.
