---
title: "Task 4 - Traffic generation"
chapter: true
weight: 5
---

### Task 4 - Traffic generation

Generate Traffic from Branch1 Primary FortiGate:

1. Connect to the Branch1 Primary FortiGate
1. Configure ping-options to initiate traffic from FortiGate's private nic (port2).
    * Source IP depends on which Branch1 FortiGate is primary br1fgt1 or br1fgt2
        * `execute ping-options source 172.16.2.4`
        * `execute ping-options source 172.16.2.5`
    * Set the ping repeat count
        * `execute ping-options repeat-count 100`

1. Initiate a ping to Spoke11 and Spoke12 Linux VMs (10.11.1.4 and 10.12.1.4)
    * `execute ping 10.11.1.4`
    * `execute ping 10.12.1.4`

    ![traffic1](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/branch-fgt-to-spoke-01.jpg)

    ![traffic2](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/traffic2.jpg)

Generate Traffic from Branch1 Linux VM:

1. Enable serial console access on Branch1 Linux VM
    * **Select** VM **sdwan-USERXX-workshop-br1lnx1**
    * **Click** "Boot diagnostics"
    * **Click** "Settings"
    * ***Select** **Enable with managed storage account (recommended)**
    * **Click** Save

        ![bootdiagnostics1](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/boot-diagnostics-01.jpg)
        ![bootdiagnostics2](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/boot-diagnostics-02.jpg)
        ![bootdiagnostics3](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/boot-diagnostics-03.jpg)

1. Ping from VM Serial Console
    * **Click** "Serial Console"

    * Initiate a ping to Spoke11 and Spoke12 Linux VMs
    * Does it work?

        ```bash
        ping 10.11.1.4
        ping 10.12.1.4 
        ```

    ![console3](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/ssh-br-lnx-console-01.jpg)

    ![traffic3](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/traffic3.jpg)

* The current state of the Architecture is shown below.

    ![global-step3](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/sdwan_architecture_03.jpg)
