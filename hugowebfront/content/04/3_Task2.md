---
title: "Task 2 - Azure Route Server"
chapter: true
weight: 3
---

### Task 2 - Check Azure Route Server Configuration and Learned Routes

1. **Select** the Azure Route Server **USERXX-workshop-sdwan-RouteServer** contained within your Resource Group.

    ![routeserver](images/routeserver.jpg)

1. **Click** on Peers on the left side of the menu, verify the connection to the Hub FortiGates
1. **List** the routes learned by Azure Route Server, run the commands below from your Azure Cloud Shell

* The variable `${USER}` in the commands reads your username from the environment

```bash
az network routeserver peering list-learned-routes -g ${USER}-workshop-sdwan --routeserver ${USER}-workshop-sdwan-RouteServer --name sdwan-fgt1
az network routeserver peering list-learned-routes -g ${USER}-workshop-sdwan --routeserver ${USER}-workshop-sdwan-RouteServer --name sdwan-fgt2
```

> The passive FortiGate will produce empty output

```json
{
  "RouteServiceRole_IN_0": [],
  "RouteServiceRole_IN_1": [],
  "value": null
}
```
