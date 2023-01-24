---
title: "Chapter 8 Discussion"
chapter: true
weight: 8
---

## ***Discussion Points During a Demo - Chapter 8***

Azure Virtual WAN and Azure Route Server cannot both supply routing information in the same VNET, because both supply BGP. FortiGate NVAs can be deployed in an Azure vWAN a few different ways, in this scenario the FortiGates were deployed in their own VNET and traffic was directed to the FortiGate VNET using route tables.

FortiGates integrated in to the Azure vWAN hub to support SD-WAN is currently available. FortiGates supporting Firewall services integrated in to the vWAN hub is coming in 2023. The current limitation is related to [Azure routing intent](https://azure.microsoft.com/en-us/blog/simplify-connectivity-routing-and-security-with-azure-virtual-wan/)

Azure Virtual WAN can greatly simplify connectivity but there are routing considerations, when routes should be propagated and when they should not. Additionally attention should be given to VNET layout with respect to east-west and north-south traffic flows.

## Key questions during your demo - Chapter 8

* How large is your Cloud presence?
* Would your Cloud deployments benefit from Azure vWAN or would Azure Route Server suffice?
* Could you Cloud deployment be managed through route tables, user defined routes and FortiGate static routes?

***
