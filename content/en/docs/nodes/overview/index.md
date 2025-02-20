---
Title: "Overview"
linkTitle: "Overview"
weight: 15
---

### Stats

The Node overview page shows performance and network traffic data.

Supported time windows are selectable at the top. VPN and network statistics can be targeted to specific virtual networks and interfaces.

![img](node-overview.png)

![img](node-overview2.png)

{{<fields>}}
{{<field "Node Performance" >}}
shows CPU, disk, and memory usage percentages
{{</field >}}
{{<field "VPN Traffic Volume" >}}
shows data usage sent and received, across all VPNs and for the selected virtual network
{{</field >}}
{{<field "Traffic Volume" >}}
shows data sent and receives, across all interfaces and for the selected interface
{{</field >}}
{{<field "Connected Peers" >}}
shows the number of other nodes connected. This will change based on the node type - gateways connect to all edge nodes, while edge nodes only connect to gateways.(LINK HUB GATEWAY PAGE WHEN DOCUMENTED)
{{</field >}}
{{<field "VPN Flows" >}}
shows new and active flows, across all VPNs and for the selected virtual network
{{</field >}}
{{<field "TCP Errors" >}}
shows TCP errors across all interfaces
{{</field >}}
{{</fields>}}
