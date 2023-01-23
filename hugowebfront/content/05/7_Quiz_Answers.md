---
title: "Chapter 5 Quiz Answers"
chapter: true
weight: 7
---

### Chapter 5 - QUIZ Answers

1. **Why has the Azure Route Server (ARS) injected Branch site CIDRs to the Spoke VNET protected subnet but not the FortiGate private subnet?**

    * Route propagation into the FortiGate private subnet is set to no.

1. **The Branch external load balancer has two front end public IP. How do we ensure that traffic egressing Branch1 on port1 (isp1) always has the same public IP applied? Same for traffic egressing Branch1 on port3 (isp2)?**

    * By using outbound rules associated to backend pools connected to those ports on each FortiGate.

***
