---
title: "Chapter 4 Quiz Answers"
chapter: true
weight: 7
---

### Chapter 4 - QUIZ Answers

1. **What was missing to allow the FortiGates to retrieve SDN connector filters?**

    * The FortiGate's management interfaces need access to the Azure APIs via a public IP address. This required adding a backend pool for the FortiGate management interfaces and a TCP load balancing rule to let the API response to an internal request back through the external load balancer.

1. **Why is the FortiGate only able to retrieve the SDN connector filters in its own Resource Group?**

    * The FortiGate VM Azure Identity was given the "Reader" role with the scope of the Resource Group.

1. **Why is the Branch FortiGate able to reach the remote Spoke VNETs VMs (10.11.1.4 and 10.12.1.4) but the Linux VM behind the Branch1 FortiGate cannot?**

    * The Linux VM does not know how to get to the FortiGate because no default route was defined for the route table which controls the subnet the Linux VM is in.

1. **FortiGates at Branch1 and Branch2 site are both behind Azure Load Balancers (behind NAT). Will Branch1 to Branch2 traffic successfully establish an ADVPN shortcut?**

    * Yes

***
