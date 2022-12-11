---
title: "Production Status Tags"
date: 2022-12-07
description: >
  Production status tags for organizing large Trustgrid deployments
---

It is recommended that Customers use a Tag to indicate if nodes are currently in production or not. For example, you may wish to have a tag such as prod_status with possible values like

- `deploying` for devices still being deployed
- `production` for devices actively in user
- `decommission` for devices that are being removed

{{<alert>}}
It’s important to have these tag names and values be consistent within the organization including case. `Production` and `production` would be viewed as two different values, e.g.
{{</alert>}}
