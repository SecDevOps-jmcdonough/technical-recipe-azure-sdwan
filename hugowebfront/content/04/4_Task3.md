---
title: "Task 3 - SDN Object"
chapter: true
weight: 4
---

### Task 3 - Create a Dynamic SDN object [troubleshooting required]

* Can the Hub FortiGate Azure SDN Connector read the Azure environment?
  * **Troubleshoot and Make the required changes to allow the FortiGate to retrieve the SDN filters.**

    * Hub FortiGate debug the Azure SDN Connector

      ```bash
      diagnose debug application azd -1
      diagnose debug enable
      ```

  * Hints:

    ***

    * FGT Branch3 is able to retrieve the filters, why that is not the case for the FortiGates behind Load Balancers?
    * FGT Branch3 is standalone, all other FortiGates are in A-P HA, how does that affect traffic to retrieve SDN information?
    * Hub External Load Balancer needs a management nic backend pool and a TCP rule, any port suffices. This rule is about letting TCP traffic out. The External Load Balancer will let the response traffic back in because the traffic originated internally.

    ![sdn fail](images/sdn-fail.jpg)

1. **Create** a backend pool on the Hub load balancer using the Hub FortiGate Management Interfaces

    * 10.10.4.4
    * 10.10.4.5

    ![mgmt be pool](images/mgmt-backend-pool.jpg)

    ![mgmt be pool list](images/mgmt-backend-pool-list.jpg)

1. Create a TCP Load Balancer Rule, any port will do, e.g. 13000. This rule will allow TCP response traffic back through the load balancer, when to a TCP request originated from a device in a backend pool associated to the load balancer.

    ![tcp rule](images/tcp-rule.jpg)

1. **Create** a dynamic address object on the Hub FortiGate, named `Spoke_VNETs` that resolves to the Spoke VNETs VMs

    ![Dynamic Address Object](images/dynamic-address-object.jpg)

1. **Use** the object in an existing Policy named `Branch to Cloud` to restrict traffic coming from the Branches to only VMs in the Spoke VNETs.

    ![Branch to Cloud Policy](images/policy3.jpg)
