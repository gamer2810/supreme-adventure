---
title: Get a FREE Kubernetes cluster with Oracle Cloud Infrastructure
date: February 4, 2025 5:05 PM
categories:
  - cloud
tags:
  - oci
  - kubernetes
  - free
  - k8s
  - arm64
  - cloud-platform
description: "Post migration from my previous blog. Reference:
  https://me.k3k.dev/2023/01/29/get-a-free-kubernetes-cluster-with-oracle-cloud\
  -infrastructure.html"
toc: true
comments: true
math: false
---
# Free K8S cluster

# Warning

1/ I will not take responsibility if you are charged with OCI usage from following this guide. There are many configs that I can’t possibly cover in this post that will incur usage cost.

2/ As the computing shape we use runs on the ARM64 architecture. Check the Docker images you will run if they have an ARM64 release.

# Steps

# 0/ Get basic knowledge

You should at least know about Terraform, Docker, Kubernetes to follow this guide.

## 1/ Get the cluster online

Pretty much following this quickstart guide

[terraform-oci-oke/quickstart.adoc at main · oracle-terraform-modules/terraform-oci-oke](https://github.com/oracle-terraform-modules/terraform-oci-oke/blob/main/docs/quickstart.adoc)

**Important:** To keep the cluster running on Always Free resource, you have to change these settings:

*  Turn off bastion host and operator host as their setup script does not work well with ARM computing shapes (VM).

```bash
create_bastion_host = false
create_operator                    = false
```

*  Allow public access to K8S API. As we disabled operator host, we will install and use kubectl on our local machine to control the cluster.

```bash
control_plane_type           = "public"
```

*  Config your node pool to use the VM.Standard.A1.Flex shape.

Oracle provides 4 CPU - 24 GB RAM of this shape for free every month. You can split these however you like but know that each node will have 50GB of boot volume attached and you only have 200GB for free. For that reason I will config mine with 2 nodes, each with 2 CPU and 12 GB of RAM.

```bash
np1 = {
   shape            = "VM.Standard.A1.Flex",
   ocpus            = 2,
   memory           = 12,
   node_pool_size   = 2,
   boot_volume_size = 50,
   placement_ads    = [1]
  }
```

Don’t bother with the calico, metric server, etc. settings because they are configured to be installed from your operator host. Since we don’t have one, they won’t be install on your cluster.

It is **highly encouraged** that you read about what the Terraform script setups as configs may incur cost:

[terraform-oci-oke/topology.adoc at main · oracle-terraform-modules/terraform-oci-oke](https://github.com/oracle-terraform-modules/terraform-oci-oke/blob/main/docs/topology.adoc)

[terraform-oci-oke/instructions.adoc at main · oracle-terraform-modules/terraform-oci-oke](https://github.com/oracle-terraform-modules/terraform-oci-oke/blob/main/docs/instructions.adoc)

# 2/ Connect to your cluster

Install kubectl on your local machine

Find your cluster in the OCI console at: [https://cloud.oracle.com/containers/clusters](https://cloud.oracle.com/containers/clusters?region=ap-singapore-1)

Click on access cluster

Copy and run the kubeconfig command from the popup, it should look like:

> To access the kubeconfig for your cluster via the VCN-Native public endpoint, copy the following command: 

oci ce cluster create-kubeconfig --cluster-id ocid1.cluster.xxx --file $HOME/.kube/config --region yyyy --token-version 2.0.0 --kube-endpoint PUBLIC_ENDPOINT

# 3/ Setup the essentials

## Calico

The cluster comes with Flannel as its CNI. I find it quite buggy and not being actively maintained. We can switch to Calico with a few commands from this handy guide: 

[Migrate a Kubernetes cluster from flannel/Canal to Calico](https://projectcalico.docs.tigera.io/getting-started/kubernetes/flannel/migration-from-flannel)

## Metric server

Installing this is required to run the `top` commands.

Just run 

```bash
kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml
```

# 4/ Have fun

Now you have a up-and-running K8S cluster that you can experiment with for free.
