---
tags: ["node", "concepts"]
title: "Thresholds"
linkTitle: "Thresholds"
weight: 19
---

{{% pageinfo %}}
Thresholds provide a way to trigger events when different measurements exceed a given value. Thresholds configured at the node level can override [Domain Thresholds]({{<ref "/docs/domain/thresholds" >}}).
{{% /pageinfo %}}

To view and configure thresholds, a user will need `nodes::configure::thresholds` permissions.

Navigate to a node, and click `Thresholds` under the `System` section.

![img](list.png)

Note that overridden thresholds have a yellow square icon next to them.

### Load Thresholds

Load thresholds measure the health of the node itself.

{{<fields>}}
{{<field "Name" >}}
The name of the threshold. This will be available in generated events.
{{</field >}}

{{<field "Telemetry" >}}
The metric to monitor. Options are CPU usage (%), memory usage (%), disk usage (%), and embryonic flows (absolute count).
{{</field >}}

{{<field "Threshold" >}}
The value that must be exceeded for an event to be generated.
{{</field >}}

{{<field "Duration" >}}
The time period to measure. If the threshold is exceeded for this duration, an event will be generated.
{{</field >}}
{{</fields>}}

### Network Thresholds

Network thresholds measure the health of the network from the node's perspective.

{{<fields>}}
{{<field "Name" >}}
The name of the threshold. This will be available in generated events.
{{</field >}}

{{<field "Telemetry" >}}
The metric to monitor. Options are latency (ms), bandwidth in (Mbps), and bandwidth out (Mbps).
{{</field >}}

{{<field "Threshold" >}}
The value that must be exceeded for an event to be generated.
{{</field >}}

{{<field "Duration" >}}
The time period to measure. If the threshold is exceeded for this duration, an event will be generated.
{{</field >}}

{{<field "Target" >}}
For latency, target node to measure the latency to. For bandwidth measurements, the interface to measure the bandwidth on.
{{</field >}}
{{</fields>}}
