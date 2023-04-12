---
title: "Task 3 - VWAN Routing"
chapter: true
weight: 4
---

### Task 3 - VWAN Routing and VNET Connection Configuration

Create Virtual WAN Route Tables

1. **Select** your virtual WAN - **sdwan-USERXX-workshop-vwan**
1. **Select** your virtual Hub - **USERXX-vwanhub**
1. **Click** "Route Tables"
1. **Click** "+ Create route table"

    ![vwan-rt1](../images/vwan-rt-01.jpg)
    ![vwan-rt2](../images/vwan-rt-02.jpg)

1. **Create** two Route Tables
    * Name - `Spoke-VNETS`
    * Name - `FGT-VNET`
1. **Click** "Review + create"
1. **Click** "Create"

    ![vwan-rt3](../images/vwan-rt-03.jpg)
    ![vwan-rt4](../images/vwan-rt-04.jpg)
    ![vwan-rt5](../images/vwan-rt-05.jpg)

Create Virtual WAN  VNET Connections

1. **Select** your virtual WAN - **sdwan-USERXX-workshop-vwan**
1. **Click** "Virtual Network Connections"

## Add Spoke11 VNET

1. **Click** "+ Add Connection"
    * Connection Name - `spoke11`
    * Hubs - "USERXX-vwanhub"
    * Subscription - "Internal-Training"
    * Resource group - "USERXX-workshop-sdwan"
    * Virtual Network - "USERXX-workshop-sdwan-spoke11"
    * Propagate to none - "No"
    * Associate Route Table - "Spoke-VNETS"
    * Propagate to Route Tables - "FGT-VNET"
    * Leave other settings unchanged
1. **Click** "Create"

## Add Spoke12 VNET

1. **Click** "+ Add Connection"
    * Connection Name - `spoke12`
    * Hubs - "USERXX-vwanhub"
    * Subscription - "Internal-Training"
    * Resource group - "USERXX-workshop-sdwan"
    * Virtual Network - "USERXX-workshop-sdwan-spoke12"
    * Propagate to none - "No"
    * Associate Route Table - "Spoke-VNETS"
    * Propagate to Route Tables - "FGT-VNET"
    * Leave other settings unchanged
1. **Click** "Create"

## Add FortiGate Hub VNET

1. **Click** "+ Add Connection"
    * Connection Name - `FGT-VNET`
    * Hubs - "USERXX-vwanhub"
    * Subscription - "Internal-Training"
    * Resource group - "USERXX-workshop-sdwan"
    * Virtual Network - "USERXX-workshop-sdwan-hub1"
    * Propagate to none - "No"
    * Associate Route Table - "FGT-VNET"
    * Leave other settings unchanged
1. **Click** "Create"

    ![vwanconnection1](../images/vnetconnection-01.jpg)
    ![vwanconnection2](../images/vnetconnection-02.jpg)
    ![vwanconnection3](../images/vnetconnection-03.jpg)

Configure Spoke-VNETS Route Table

1. **Select** your virtual WAN - **sdwan-USERXX-workshop-vwan**
1. **Select** your virtual Hub - **USERXX-vwanhub**
1. **Click** "Route Tables"
1. **Click** "Spoke-VNETS"
1. **Add** Route
    * Route Name - `default`
    * Destination Type - "CIDR"
    * Destination prefix - `0.0.0.0/0`
    * Next hop - "FGT-VNET"
    * Next hop IP - **Click** "Configure"
        * Next hop IP - `10.10.1.4` <-- **Primary FGT port2 ip**
1. **Click** "Confirm"
1. **Click** "Review + create"
1. **Click** "Create"

      ![vwanhubrouting1](../images/vwanhubrouting-01.jpg)
      ![vwanhubrouting2](../images/vwanhubrouting-02.jpg)
      ![vwanhubrouting3](../images/vwanhubrouting-03.jpg)

Verify that this default route has been propagated to the Spokes VNETs

1. **View** Spoke11 Linux VM nic **Effective Routes**

      ![vwanhubrouting4](../images/vwanhubrouting-04.jpg)

* The current state of the Architecture is shown below.

    ![global4](../images/sdwan_architecture_04.jpg)  
