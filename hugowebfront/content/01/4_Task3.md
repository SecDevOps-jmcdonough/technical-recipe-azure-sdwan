---
title: "Task 3 - Terraform Verifications"
chapter: true
weight: 4
---

### Task 3 - Terraform Verification

  1. Using the Terraform output, verify that you have Web and SSH access to the FortiGates.

      ![terraform4](../images/terraform-04.jpg)

      * Terraform output can be redisplayed at any point as long as you are in the `./technical-recipe-azure-sdwan/terraform/` directory, by using the command `terraform output`

        ```sh
        cd
        cd ./technical-recipe-azure-sdwan/terraform/
        terraform output
        ````

  1. Connect to the Branch FortiGates and check the VPN IPSec status.
  1. Connect to the Hub FortiGates and check the WAN IP.
