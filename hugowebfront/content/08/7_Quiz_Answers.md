---
title: "Chapter 8 Quiz Answers"
chapter: true
weight: 7
---

### Chapter 8 - QUIZ Answers

1. **Why were we not able to attach the Hub FortiGate VNET to vWAN until we deleted Azure Route Server?**

    * An Azure VNET cannot receive routes from the vWAN and the RouteServer at the same time.

1. **Why was the vWAN not able to inject Spoke11 and Spoke12 VNETs CIDRs to FortiGate Private UDR?**

    * Route propagation for the FortiGate route table sdwan-USERXX-workshop-hub1_fgt-priv_rt was set to no.

1. **The Hub FortiGate sdwan-USERXX-workshop-hub1_fgt-priv_rt route table configuration "Propagate gateway routes" is normally set to "yes", why did we set it to "no"?**

    * Azure RouteServer provided the routes.

1. **In the Spoke-VNETS vWAN Route Table, the next-hop is the Primary FortiGate IP. What should we add/do to handle failover?**

    * An internal load balancer could be added and use that IP as the next hop or an automation stich could be run at failover to update the Spoke-VNETS vWAN Route Table to point to the newly active FortiGate private interface.

***
