---
title: "Task 3 - TCP Traffic"
chapter: true
weight: 4
---

### Task 3 - Generate TCP traffic

1. **Ensure** that both Branch1 FortiGates in the cluster are up and running
1. **Login** to the Branch1 Linux VM serial console - **sdwan-USERXX-workshop-br1lnx1**
1. **Generate** an SSH session to the Spoke Linux VM - **sdwan-USERXX-workshop-spoke11-subnet1-lnx**

   ```bash
   ssh USERXX@10.11.1.4
   ```

1. **Generate** from Spoke Linux VM SSH session a continuous stream of TCP connections to track the failover event

  ```bash
  while true
  do
    date
    curl -I -sw '%{http_code}'  https://www.fortinet.com
    echo -e "\n================="
    sleep 1
  done
  ```

  [continuoustcpping1](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/continuoustcpping-01.jpg)

1. **Login** to the Branch1 Primary FortiGate.
    * It may be - **sdwan-USERXX-workshop-br1-fgt1** or **sdwan-USERXX-workshop-br1-fgt2**
1. **Initiate** a failover via the CLI

* Monitor the SSH connection
* Did the TCP connection resume?
  * The TCP session will not resume, this is due to the Azure Load Balancer not maintaining TCP sessions in a failover.
