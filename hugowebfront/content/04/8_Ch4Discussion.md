---
title: "Chapter 2 Discussion"
chapter: true
weight: 8
---

## ***Discussion Points During a Demo - Chapter 4***

Azure Virtual Network (VNET) Peering provides the ability to connect multiple VNETs together and direct traffic flow based on existence of a gateway in a connected peer or with a user defined route (UDR) in a route table.

Utilizing an Azure Route Server (ARS) and setting the FortiGates as a BGP peers enables the FortiGates to be updated with newly available routes or the removal of routes as VNETs are peered or when a peering relationship is removed.

From a FortiGate Policy perspective the ability to be dynamically aware of a changing environment is provided by the Azure SDN Connector. The SDN Connector is continually polling the environment and logging the changes, FortiGate dynamic address objects and Automation Stitches can take full advantage of the SDN connector to update policy and effect internal and external changes.

An Azure Route Table provides a way to specifically direct traffic, when used in conjunction with an ARS or FortiGate static routes protected workload traffic can be fully managed.

Several settings in Azure determine traffic flow review the following for Azure Routing

* [Azure Route Server](https://learn.microsoft.com/en-us/azure/route-server/)
* [Azure Route Tables](https://learn.microsoft.com/en-us/azure/virtual-network/tutorial-create-route-table-portal)

## Key questions during your demo - Chapter 4

* Do you currently use, planning to use or just learning about VNET peering?
* Are you aware of the capabilities that the Azure SDN Connector provides?
* Are you using dynamic address objects or Automation Stitches?

***
