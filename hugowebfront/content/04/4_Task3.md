---
title: "Task 3 - SDN Object"
chapter: true
weight: 4
---

### Task 3 - Create a Dynamic SDN object [troubleshooting required]

Can the Hub FortiGate Azure SDN Connector read the Azure environment?

* **Troubleshoot and Make the required changes to allow the FortiGate to retrieve the SDN filters.**

On the Hub FortiGate view the Azure SDN Connector

1. **Login** to the Hub FortiGate
1. **Click** "Security Fabric"
1. **Click** "External Connectors"
1. **Hover** Over Azure Connector - "AzureSDN"
1. **Click** "View Connector Objects"

On the Hub FortiGate debug the Azure SDN Connector

![sdn fail1](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/sdn-fail-01.jpg)
![sdn fail2](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/sdn-fail-02.jpg)

1. **Open** a FortiGate CLI session
1. **Enter** the SDN connector debug commands

      ```bash
      diagnose debug application azd -1
      diagnose debug enable
      ```

In a few minutes the output will indicate the SDN Connector's inability to make an call to the Azure Management API.

![sdn fail3](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/sdn-fail-03.jpg)

Hints:
***

* Branch3 FortiGate is able to retrieve the filters, why that is not the case for the FortiGates behind Load Balancers?
* Branch3 FortiGate is standalone, all other FortiGates are in Active-Passive HA, how does that affect traffic to retrieve SDN information?
* Hub External Load Balancer needs a management nic backend pool and a TCP rule, any port suffices. This rule is about letting TCP traffic out. The External Load Balancer will let the response traffic back in because the traffic originated internally.

1. **Create** a backend pool on the Hub load balancer using the Hub FortiGate Management Interfaces

    * Name - `mgmt-pool`
    * Interfaces
        * 10.10.4.4
        * 10.10.4.5

    ![mgmt be pool1](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/mgmt-backend-pool-01.jpg)
    ![mgmt be pool2](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/mgmt-backend-pool-02.jpg)
    ![mgmt be pool3](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/mgmt-backend-pool-03.jpg)

1. Create a TCP Load Balancer Rule, any port will do, e.g. 13000. This rule will allow TCP response traffic back through the load balancer, when to a TCP request originated from a device in a backend pool associated to the load balancer.

    * Name - `tcp-rule`
    * Frontend IP address - "hub-pip1"
    * Backend pool - "mgmt-pool"
    * Protocol - "TCP"
    * Port - `13000`
    * Backend port - `13000`
    * Health probe - hub1-elb1-probe (TCP:8008)
    * Session Persistence - "None"
    * Idle timeout (minutes) - "4"
    * TCP reset - "Disabled"
    * Floating IP - "Disabled"
    * Outbound source network address translation (SNAT) - "Use default outbound access"

    ![tcp rule1](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/tcp-rule-01.jpg)

Utilize the SDN connector results in a Dynamic Address Object and Policy

1. **Login** to the Hub FortiGate
1. **Click** "Policy & Objects"
1. **Click** "Addresses"
1. **Create New** dynamic address object on the Hub FortiGate, named `Spoke_VNETs` that resolves to the Spoke VNETs VMs

    * Name - `Spoke_VNETs`
    * Type - "Dynamic"
    * SDN Connector - "AzureSDN"
    * SDN address type - "Private"
    * Filter
        * Vnet=**userxx**-workshop-sdwan-spoke11
        * Vnet=**userxx**-workshop-sdwan-spoke12
    * Interface - "priv (port2)"

    ![Dynamic Address Object1](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/dynamic-address-object-01.jpg)

**Use** the address object in an existing Policy to restrict traffic coming from the Branches to only VMs in the Spoke VNETs.

1. **Click** "Policy & Objects"
1. **Click** "Firewall Policy"
1. **Edit** the policy "Branch to Cloud"
1. **Set** the policy destination to "Spoke_VNETs"

    ![Branch to Cloud Policy1](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/policy-branch-to-spoke-01.jpg)
    ![Branch to Cloud Policy2](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/policy-branch-to-spoke-02.jpg)
    ![Branch to Cloud Policy3](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/policy-branch-to-spoke-03.jpg)
