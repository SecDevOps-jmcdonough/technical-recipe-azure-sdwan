---
title: "Task 3 - Effective Routes"
chapter: true
weight: 4
---

### Task 3 - Check Effective Routes

Check the Effective Routes for Spoke 11 Linux VM

1. **Click** on Spoke11 Linux VM **sdwan-USERXX-workshop-spoke11-subnet1-lnx**
1. **Click** on Networking
1. **Click** on the VM Nic **sdwan-USERXX-workshop-spoke11-subnet1-lnx-nic**
1. **Click** on **Effective routes**

    ![effectiveroutes1](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/effectiveroutes-lnx-01.jpg)
    ![effectiveroutes2](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/effectiveroutes-lnx-02.jpg)

1. **Check** that Azure Route Server has injected the Branch sites CIDRs learned from the FortiGate

    ![effectiveroutes3](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/effectiveroutes-lnx-03.jpg)

Check the Effective Routes for Hub FortiGate

1. **Click** on the Hub FGT **sdwan-USERXX-workshop-hub1-fgt1**
1. **Click** on Networking
1. **Click** on the VM Nic port1 Nic **hub1-fgt1-port1**
1. **Click** on **Effective routes**

    ![effectiveroutes4](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/effectiveroutes-lnx-04.jpg)
    ![effectiveroutes5](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/effectiveroutes-lnx-05.jpg)

Has Azure Route Server injected the Branch sites CIDRs learned from the FortiGates?

* In this case it is the FortiGate that knows how to route from the Hub to the Branches, but these routes are not given to the Azure Route Server. These BGP routes are learned through the IPsec VPN connections.
