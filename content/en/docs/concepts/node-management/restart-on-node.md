---
Title: "Restart the Trustgrid Service on a Node"
Date: 2023-1-3
---

{{% pageinfo %}}
Restarting the Trustgrid service is faster than a full node reboot and resolves many non-recurring problems.
{{% /pageinfo %}}

1. Go to the `Node` detail page for the node affected.

2. Select `Restart Service` from `Action` dropdown

![img](/docs/concepts/node-management/restart.png)

3. Click `Execute`

4. the node agent will restart (Node host will not restart)

5. Expect the node to alert for disconnection and connection.



