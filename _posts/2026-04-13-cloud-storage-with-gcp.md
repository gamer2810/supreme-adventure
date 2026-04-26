---
title: Cloud Storage with GCP
date: April 13, 2026 1:20 PM
categories:
  - cloud-computing
tags:
  - gcp
  - cloud-storage
  - google-cloud
description: "This is part 3 of my notes for the course: Google Cloud
  Fundamentals: Core Infrastructure."
toc: true
comments: true
math: false
image: false
---
# Cloud Storage

File is stored as Binary large-object (BLOB). 

Suitable for backing up and archiving content online.

Files are organized into buckets. A bucket name has to be globally unique. You can choose where to store and serve your data: Multi-region, Dual-Region, Region, and Zones.

These options offer different resiliency and cost.

The other option you can make to your bucket is the **storage tier**. This option let you reduce storage cost if you don't need to access data in the bucket frequently.

## Permission
You can make *uniform* rules that apply equally to a group of users. Or you can define *fine-grain* rules to allow access for specific people.

## Data Protection
These are paid addons that increase your data safety.

**Soft-delete**: Data will be kept for a specified amount of time before being deleted permanently. You can recover data within this period of time.

**Versioning**: Keeping multiple copies of data.

## Transfer Job
You can transfer data from multiple sources into buckets on Google Cloud.

You can either transfer in batch for one-time migration or use Change Data Capture for continuous streaming of new data to your bucket.

# Cloud SQL
This service lets you quickly create a SQL database on Google Cloud. 

You can have up to:
- 128 CPU cores
- 64TB of storage

in one instance.

# Spanner
Spanner is a fully managed relational database. It supports horizontal scaling through Spanner nodes.

This service is helpful when you need global synchronicity/consistency of data.

# Firestore
Firestore is a NoSQL cloud database.

Data is stored as documents and therefore does not support SQL. However, Firestore supports transactional behavior for data.

Firestore uses online and offline data synchronization.

# Bigtable
Bigtable is a NoSQL that is specialized for massive workloads and high throughput. 

This is suitable for analytical applications where you need to read and transform terabytes of data.

# Choosing the right storage options
[Google's Guide on Storage Solution](https://cloud.google.com/products/storage)


