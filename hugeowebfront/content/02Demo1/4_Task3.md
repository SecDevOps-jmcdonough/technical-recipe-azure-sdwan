---
title: "Task 3 - Hub and Spoke VPN Verification"
chapter: true
weight: 4
---
### Task 3 - Hub and Branch VPN Connectivity Verifications

Verify that the FortiGates are responding to Azure Load Balancer Health Checks

1. **Select** the Hub External Load Balancer **sdwan-USERXX-workshop-hub1-elb1**
1. **Click** on Insights - Click the "Refresh" button a few times, eventually (~30 seconds) the FortiGate reachability will be indicated.

    ![hub-lb-insights](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/externallbinsights.jpg)

1. **Verify** that the VPN connections from the Branch to the Hub are UP

    ![vpn](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/vpnup.jpg)

1. **Verify** that the BGP peering with the Hub is UP and that the Branch FortiGate learned the Hub and other Branches' CIDRs. Run the Command `get router info routing-table all` on all the Branch FortiGates.

* At the end of this step you should have the following architecture.

    ![global-step2](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/sdwan_architecture_02.jpg)
