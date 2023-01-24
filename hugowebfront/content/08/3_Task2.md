---
title: "Task 2 - Delete Peerings"
chapter: true
weight: 3
---

### Task 2 - Delete VNET Peerings / Delete Azure Route Server

1. **Select** the Hub VNET - **USERXX-workshop-sdwan-hub1**
1. **Click** on Peerings
1. **Delete** the Hub to Spoke VNET peerings
    * hub-to-spoke11
    * hub-to-spoke12

    ![peeringdelete1](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/peeringdelete-01.jpg)
    ![peeringdelete2](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/peeringdelete-02.jpg)

Deleting a peering in the Azure Portal from one virtual network will delete its corresponding peering from the peered VNET. When using the Azure API to create or remove peerings, directly or via IaC tools, e.g., Terraform, each side of the peering needs to be created or deleted.

Delete the Azure Route Server. The Azure VWAN or the Azure Route Server can provide routing for a VNET **but not both**. To continue with the Azure VWAN setup the Azure Route Server needs to be deleted.

1. **Locate** Azure Route Server
1. **Click** Delete

      ![deletears1](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/deletears-01.jpg)
      ![deletears2](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/deletears-02.jpg)

Deleting the Azure Route Server will take several minutes to complete.
