---
title: "Task 1 - Route Tables - UDRs"
chapter: true
weight: 2
---

### Task 1 - Create a User Defined Route (UDR) in the Branch route tables

1. **Click** on the Branch1 private route table **sdwan-USERXX-workshop-branch1_rt**
1. **Click** Routes
1. **Add** a default route for `0.0.0.0/0` that points to the Branch1 **Internal Load balancer listener IP**
    * Name - `default`
    * Address prefix destination - "IP Addresses"
    * Destination IP addresses/CIDR ranges - `0.0.0.0/0`
    * Next hop type - "Virtual appliance"
    * Next hop address
      * Branch1 - `172.16.2.10`
      * Branch2 - `172.17.2.10`
      * Branch3 - `172.17.2.4`
1. **Repeat** for **Branch2** and **Branch3** Route Tables
  
    * Be sure to use the correct IP as the next hop, that is the correct internal Load balancer frontend IP or FortiGate internal interface.

    * The next hop is a load balancer or a stand-alone FortiGate.

    ![add udr branch1](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/add-defaultroutebranch1-01.jpg)
    ![add udr branch2](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/add-defaultroutebranch1-02.jpg)
    ![add udr branch3](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/add-defaultroutebranch1-03.jpg)
    ![add udr branch4](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/add-defaultroutebranch1-04.jpg)
