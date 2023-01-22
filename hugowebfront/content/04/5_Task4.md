---
title: "Task 4 - Traffic generation"
chapter: true
weight: 5
---

### Task 4 - Traffic generation

* Generate Traffic from Branch1 Primary FortiGate:  
  1. Connect to the Branch1 Primary FortiGate
  2. Configure ping-options to initiate traffic from FortiGate's private nic (port2).
      * `execute ping-options source 172.16.2.5` - source IP depends on which Branch1 FortiGate is primary br1fgt1 or br1fgt2
      * `execute ping-options repeat-count 100`
  3. Initiate a ping to Spoke11 and Spoke12 Linux VMs (10.11.1.4 and 10.12.1.4)
      * `execute ping 10.11.1.4`
      * `execute ping 10.12.1.4`

    ![traffic2](images/traffic2.jpg)

    ![traffic1](images/traffic1.jpg)

* Generate Traffic from Branch1 Linux VM:  
    1. Enable serial console access on Branch1 Linux VM
        * Click on the VM **sdwan-USERXX-workshop-br1lnx1**
        * Go to Boot diagnostics -> Settings ->  Select **Enable with managed storage account (recommended)**
        * Click Save

            ![console1](images/ssh-br-lnx-console1.jpg)
            ![console2](images/managed-storage.jpg)

    2. Go to the VM Serial Console
        ![console3](images/ssh-br-lnx-console3.jpg)

    3. Initiate a ping to Spoke11 and Spoke12 Linux VMs

        ```bash
        ping 10.11.1.4
        ping 10.12.1.4 
        ```

        ![traffic3](images/traffic3.jpg)

    4. Does it work?

* At the end of this step  you should have the following architecture

    ![global-step3](images/sdwan_architecture_03.jpg)
