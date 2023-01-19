---
title: "task 3 - Terraform Verifications"
chapter: true
weight: 4
---

### Task 3 - Terraform Verifications

  1. Using the Terraform output, verify that you have Web and SSH access to the FortiGates.

      ![output](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/output.jpg)

      * Terraform output can be redisplayed at any point as long as you are in the `./se-conf-sdwan-workshop/se-summit/` directory, by using the command `terraform output`

        ```sh
        cd
        cd se-conf-sdwan-workshop/se-summit/
        terraform output
        ````

  1. Connect to the Branch sites FortiGates and check the VPN status.
  1. Connect to the Hub FortiGates and check the WAN IP

{{% notice warning %}}
<p style='text-align: left;'>
The examples and sample code provided in this workshop are intended to be consumed as instructional content. These will help you understand how various Fortinet and Azure services can be architected to build a solution while demonstrating best practices along the way. These examples are not intended for use in production environments without full understanding of how they operate.
</p>
{{% /notice %}}