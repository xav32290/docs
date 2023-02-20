---
title: "Layer 3 - HA Edge to AWS"
description: Connect a highly-available edge cluster to AWS
---

In this scenario a clustered pair of active/passive edge nodes at each edge location connects to a pair of active/passive clustered gateway nodes in an AWS VPC and layer 3 traffic is routed between the edge location and AWS. 

This configuration allows for the loss of one node at each site without a loss of connectivity between the edge location and AWS. Upon node failover, the active cluster member is switched to the second node and the VPC route table is updated to route traffic destined for the Trustgrid network through the ENI of the second node, allowing traffic flow to continue. Failback to the original active cluster member happens when the original active node recovers from the event that caused the failover, and the VPC route table is updated to route traffic destined fro the Trustgrid network through the ENI of the data NIC on the original active node. 

Inside NATs are used to translate local IP addresses to IP addresses on the Trustgrid network.  

![Network Topology](aws-topology.png)

### Network Information

| Local Network CIDR | Location |
| ------------------ | -------- |
| 192.168.10.0/24 | AWS VPC Subnet |
| 172.16.10.0/24 | Edge location 1 |
| 172.16.20.0/24 | Edge location 2 |
| 172.16.30.0/24 | Edge location 3 |

### Route Configuration

In this example, the Trustgrid network is `10.100.0.0/16`.

| Trustgrid Network CIDR | Destination Node |
| ---------------------- | ---------------- |
| 10.100.100.0/24 | AWSCluster |
| 10.100.10.0/24 | EdgeCluster1 |
| 10.100.20.0/24 | EdgeCluster2 |
| 10.100.30.0/24 | EdgeCluster3 |

### Inside NAT Configuration

| Local CIDR | Network CIDR | Node | Description |
| ---------- | ------------ | ---- | ----------- |
| 192.168.10.15/32 | 10.100.100.15/32 | AWSCluster | Application server behind AWSCluster nodes |
| 172.16.10.15/32 | 10.100.10.15/32 | EdgeCluster1 | MySQL server behind EdgeCluster1 nodes |
| 172.16.20.15/32 | 10.100.20.15/32 | EdgeCluster2 | MySQL server behind EdgeCluster2 nodes |
| 172.16.20.20/32 | 10.100.20.20/32 | EdgeCluster2 | SFTP server behind EdgeCluster2 nodes |
| 172.16.30.15/32 | 10.100.30.15/32 | EdgeCluster3 | MySQL server behind EdgeCluster3 nodes |
