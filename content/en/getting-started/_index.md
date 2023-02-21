---
title: "Getting Started"
linkTitle: "Getting Started"
menu:
  main:
    weight: 10
cascade:
  type: docs
---

## Concepts

Trustgrid is a platform that provides secure, reliable and high-performance connectivity between distributed systems and applications. The platform is designed to simplify networking for distributed enterprises by providing a software-defined network (SDN) that operates as a virtual overlay on top of existing networks, enabling organizations to build and manage their own private networks.

### Nodes

The basic building block of a Trustgrid network is a [node]({{<ref "docs/nodes">}}). Nodes are deployed on-premises or in your cloud provider and are connected to each other with TLS tunnels. Nodes can be deployed in a variety of ways, including as virtual machines, containers, or bare metal servers.

Nodes are used to enable connectivity and access for different use cases, including:

* ZTNA applications, allowing fine-grained network control for access to business applications or servers
* VPN-like functionality, allowing network address translation (NAT) and routing between nodes
* Remote container execution, allowing an admin to deploy and manage containers in edge networks
* FTP (remote or in a data center) and other layer 4 protocols

### Clusters

Nodes can be grouped into [clusters]({{<ref "docs/clusters">}}) to share configuration and provide high-availability.

### Virtual Networks

Nodes can be attached to [virtual networks]({{<ref "docs/domain/virtual-networks">}}), which provide a way to share network configuration like [routes]({{<ref "docs/domain/virtual-networks/routes">}}), NATs, and [ACLs]({{<ref "docs/domain/virtual-networks/access-policy">}}) at scale. 

### Applications

[Applications]({{<ref "docs/applications">}}) can be exposed through nodes or clusters. Access to an application can be restricted via [access policies]({{<ref "docs/applications/access-policy">}}), for example to only allow users from a specific country.

## Management

All Trustgrid nodes are entirely managed through our control plane:

* Software updates are provided through our apt repository that ensures nodes have security updates available and only run with tested software permutations
* Network, node, user, and application configuration is managed through our web portal
* Configuration changes are broadcast to nodes as needed, for example when adding routes or adding a gateway to your network

## Next Steps

The first step to try out Trustgrid is [create an account]({{<ref "getting-started/new-account">}}).