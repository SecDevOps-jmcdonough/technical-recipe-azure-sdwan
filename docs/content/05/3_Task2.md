---
title: "Task 2 - Branch to Hub"
chapter: true
weight: 3
---

### Task 2 - Generate Branch traffic to the Hub

1. **Connect** to the Branch1 Linux VM via the serial console
1. **Generate** traffic to Hub

    ```bash
     ping 10.11.1.4
     ping 10.12.1.4 
    ```

    ![console3](../images/ssh-br-lnx-console-01.jpg)

1. Why does it work now?

* Now when traffic leaves the branch linux VM the next hop is the Branch FortiGate, because the Azure route table default route.
