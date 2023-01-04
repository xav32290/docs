---
Title: "Restart the Trustgrid Service on a Node"
Date: 2023-1-4
---

{{% pageinfo %}}
Restarting the Trustgrid service is faster than a full node reboot and resolves many non-recurring problems.
{{% /pageinfo %}}

1. Go to the `Node` detail page for the node affected.

2. Select `Restart Service` from `Action` dropdown

![img](restart.png)

1. Click `Execute`

2. the node agent will restart (Node host will not restart)

3. Expect the node to alert for disconnection and connection.



