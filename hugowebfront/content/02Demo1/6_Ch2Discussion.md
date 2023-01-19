---
title: "Chapter 2 Discussion"
chapter: true
weight: 6
---

## ![Customer-Demo](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/demo_play.png) ***Discussion Points During a Dem - Chapter 2***

When discussing load balanced traffic with the customer, point out key details about the Azure Load Balancers such as the following:

* Azure LB uses 5-tuple hash for traffic distribution
* IPSec in an Active/Active configuration is not supported as session stability cannot be guaranteed to IkE rekeys, and deterministic IP termination.  
* TCP/UDP headers are rewritten to the backend pool.  HTTP/s headers are not changed.  
* Legacy applications or those requiring long-lived sessions could see performance issues due to TTL limitations on the LB.  

When connecting IPSec traffic from remote inter-regional sites, the customer's architecture could benefit from dedicated FortiGates to support IPSec.  This is a benefit where large traffic loads are supported for deep packet inspection and where there is a lot of E/W traffic.  Dedicated FortiGates for IPSec allow the opportunity to scale VPN traffic using IPSec Aggregate without impacting performance of traffic inspection.  Details on IPSec Aggregate can be found [here](https://docs.fortinet.com/document/fortigate/7.2.3/administration-guide/779201/aggregate-and-redundant-vpn).

Don't forget that the CLI is still a great place to get targeted information with a single command. For example, viewing the FortiGate known routes with the CLI command `get router info routing-table all`

## Key questions during your demo - Chapter 2

When giving this TEChnical Recipe as as demo, the following questions will provide a basis for next steps and future meetings:

* How sensitive are your applications to session timeout?  Do they require large TTL values for long-lived sessions?
* What type of VPN scaling (tunnel count and bandwidth) are required for your deployment?  
* How much east/west traffic versus north/south traffic will be supported?  
* What types of inspection will be required between various VNets?
* Is advanced BGP configuration required? (FortiGate-to-FortiGate can support advanced BGP metrics unlike Azure's services)

***