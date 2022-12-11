---
categories: ["concepts"]
tags: ["domain", "concepts"]
title: "Domain"
date: 2022-12-07
description: >
  Trustgrid domains
---

{{% pageinfo %}}
A domain is the logical grouping of nodes inside your organization.
{{% /pageinfo %}}

Domains are used to group nodes into security groups. Nodes can only connect to nodes within the same domain. Trustgrid supports domains and subdomains in the typical FQDN format (ie, customer_name.trustgrid.io, group1.customer_name.trustgrid.io). Each Trustgrid deployment will have a default domain.

Each domain must have at least one Gateway Node.
