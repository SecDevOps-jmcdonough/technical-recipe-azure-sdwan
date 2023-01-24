---
title: "Chapter 7 Discussion"
chapter: true
weight: 2
---

## ***Discussion Points During a Demo - Chapter 7***

Active/Active FortiGate deployments can scale both horizontally and vertically, additionally there is a lower interface requirement resulting in an ability to deploy smaller Azure instance types. However, SD-WAN Active/Active FortiGate deployments come with some limitations, mainly traffic asymmetry and a larger IPSEC deployment. For example, a two FortiGate Active/Active deployment would require each branch FortiGate to maintain four IPSEC connections to each Active/Active FortiGate.

Active/Passive FortiGate deployments only support vertical scalability, but only need two IPSEC connections per FortiGate Active Passive pairs.

## Key questions during your demo - Chapter 7

When giving this TEC Recipe as as demo, the following questions will provide a basis for next steps and future meetings:

* Can your applications support asymmetric traffic?
* Do you have the need to scale horizontally?

***
