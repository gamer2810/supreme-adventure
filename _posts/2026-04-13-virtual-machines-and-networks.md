---
title: Virtual Machines and Networks
date: April 13, 2026 11:17 AM
categories:
  - gcloud
tags:
  - google-cloud
  - vm
  - network
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


