---
title: "Task 4 - VWAN Traffic"
chapter: true
weight: 5
---

### Task 4 - VWAN Traffic generation

Generate traffic from the Branch1 Linux VM to a Spoke Linux VM

1. **Connect** to the Branch1 Linux Host **sdwan-USERXX-workshop-spoke11-subnet1-lnx** via the serial console
1. **Ping** Spoke11 Linux VM **sdwan-USERXX-workshop-spoke11-subnet1-lnx**

    ```bash
     ping 10.11.1.4
    ```

    ![branchtospokevwanping1](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/branch-to-spoke-vwan-ping-01.jpg)

* Does it work?
  * Azure VWAN Route Tables enable the Spoke Networks to know the route to the Hub FortiGates, however, the Branches do not know how to get to the Spoke VNETs.

    ![vwan traffic flow](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/vwan-traffic1.jpg)  

Make the required changes for ping to work

* Hints:
  ***

  * FGT Branch1 learns routes to spokes from the Hub
  * Configure the Hub FGT to advertise Spoke11 and Spoke12 CIDRs to the Branches

1. **Add** Static Routes to Spoke11 and Spoke12
1. **Click** "Network"
1. **Click** "Static Routes"

Add Spoke11

1. **Click** "+ Create New"
    * Destination - `10.11.0.0/16`
    * Gateway Address - `10.10.1.1`
    * Interface - "priv (port2)"
1. **Click** "OK"

Add Spoke12

1. **Click** "+ Create New"
    * Destination - `10.12.0.0/16`
    * Gateway Address - `10.10.1.1`
    * Interface - "priv (port2)"
1. **Click** "OK"

    ![staticroutes1](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/static-routes-01.jpg)
    ![staticroutes2](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/static-routes-02.jpg)

1. **Add** Spoke11 and Spoke12 to the list of networks under BGP configuration - via CLI or UI

    ```bash
    config router bgp
      config network
          edit 1
              set prefix 10.10.255.1 255.255.255.255
          next
          edit 2
              set prefix 10.11.0.0 255.255.0.0
          next
          edit 3
              set prefix 10.12.0.0 255.255.0.0
          next
      end
    end
    ```

    ![spokebgp1](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/spokebgp-01.jpg)
    ![spokebgp2](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/spokebgp-02.jpg)

1. Verify that Branches are now receiving Spoke11 and Spoke12 CIDRs - via CLI
    * `get router info routing-table all`

    ![branch1bgproutes1](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/branch1bgp-01.jpg)

    * Does it work now or not yet?

1. **Sniff** packets on the Hub FortiGate, are echo-requests arriving?  
    * `diagnose sniffer packet any 'net 10.11.0.0/16' 4 0 a`

    ![sniffpings1](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/sniffpings-01.jpg)

    * Traffic is egressing the Hub FortiGate on port2, but no reply?... What is missing?  

1. **Check** FortiGate Hub port2 **effective routes**?

    ![hubeffectiveroutes1](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/hub-effective-routes-01.jpg)

    * Is the vWAN propagating spoke11 and spoke12 to the Route Table attached to the FortiGate private subnet, **sdwan-USERXX-workshop-hub1_fgt-priv_rt**?

1. **Check** the Route Table  **sdwan-USERXX-workshop-hub1_fgt-priv_rt** configuration settings
1. **Select** "Yes"
1. **Click** "Save"

    ![rtconfigsettings](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/rt-config-settings-01.jpg)

    ![hubeffectiveroutes2](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/hub-effective-routes-02.jpg)

Traffic should now be flowing between Branch1 Linux VM and Spoke11 Linux VM.  If the pings are not working, try cancelling the ping and trying again.

  ![branchtospokevwanping1](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/branch-to-spoke-vwan-ping-01.jpg)
