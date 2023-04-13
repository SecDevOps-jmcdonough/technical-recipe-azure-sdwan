---
title: "Chapter 3 Discussion"
chapter: true
weight: 2
---

## ***Discussion Points During a Demo - Chapter 3***

The Azure Route Server (ASR) is used to connect NVAs to the Azure network to simplify VNet routing with external networks.  SD-WAN is a primary use case for the ASR where BGP routes are exchanged between a premise-based and the ASR to advertise premise-originated routes to the VNets and VNet routes to the premise.  For many customers, this may be a great fit.  For some customers, there may be more complex routing requirements such as multiple egress points,load balanced routes, large number of BGP peers, large volume of routes (>1000); where these needs require advanced BGP.  More complex use cases will require FortiGate to FortiGate peering in those cases.  Let your customer know about Fortinet's ability to support [advanced dynamic routing services](https://docs.fortinet.com/document/fortiswitch/7.2.2/administration-guide/939731/bgp-routing).  

## Key questions during your demo - Chapter 3

When giving this TEC Workshop as as demo, the following questions will provide a basis for next steps and future meetings:

* Describe your organizations routing requirements.  
* Does your environment require more than 8 BGP peers or more than 1000 routes
* Do you need to extend other routing protocols, such OSPF or ISIS into the Azure environment?

***
