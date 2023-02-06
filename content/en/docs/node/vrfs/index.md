---
categories: ["node"]
tags: ["vrfs", "networking"]
title: "VRFs"
date: 2023-02-06
---

### Overview
VRFs can be used to control and manipulate what traffic is allowed to pass and how it should appear on the network. VRFs are associated to an interface whether it be a physical interface / virtual network interface or other tunnel interfaces such as ipsec or gre. 

For standard use cases of source nat and/or destination nat creating a route and a NAT is sufficient. Traffic rules can be used for more advanced granular control. An applicable ACL is required for any traffic to pass as a zero trust methodology is applied. 

### Traffic Rules
Traffic rules can be used for more advanced granular traffic manipulation beyond standard source and destination nat. 
There are many more parameters that can be applied to the traffic depending on the specific use case.
When creating a traffic rule an ACL is required for traffic to pass. The available parameters are defined below.


{{< field-def "Number" >}}
The line number the rule is applied to. Rules are applied in sequential order.
{{< /field-def >}}

{{< field-def "Action" >}}
All traffic rules have an action that is applied to the associated packet. 
* Accept - The packet is allowed to be processed locally.
* Drop - The packet is dropped and not responded to
* Reject - A TCP Reset is sent in response 
* Forward - The packet is forwarded to its defined destination such as an interface or another VRF
* Mirror - Packets are not manipulated but can be mirrored for inspection purposes. 
For example passing through an IDS container such as Snort. 
* Log - The packet is not manipulated but is marked for logging
{{< /field-def >}}

{{< field-def "Ingress Interface" >}}
The traffic rule is applied to packets that ingress on this interface
{{< /field-def >}}

{{< field-def "Forward Interface" >}}
Packets are forwarded to this interface once the rule is applied
{{< /field-def >}}

{{< field-def "Forward Interface" >}}
Packets are forwarded to this interface once the rule is applied. Only configureable when a forward action is selected.
{{< /field-def >}}

{{< field-def "Protcol" >}}
The protocol that the rule should apply to. All, ICMP, TCP or UDP
{{< /field-def >}}

{{< field-def "Forward VRF" >}}
Packets are forwarded into another VRF that is associated on the node. Only configureable when a forward action is selected.
{{< /field-def >}}

{{< field-def "Source CIDR" >}}
The source network the rule should apply to
{{< /field-def >}}

{{< field-def "Destination CIDR" >}}
The destination network the rule should apply to
{{< /field-def >}}

{{< field-def "Masquerade" >}}
Translate and source all packets from the nodes interface address when enabled
{{< /field-def >}}

### Routes
Create a route for the destination CIDR desired and define the next hop and route metric. An optional description can be added.


### Address Translation
This is where NATs are created in order to translate the traffic to appear as desired on the network.
