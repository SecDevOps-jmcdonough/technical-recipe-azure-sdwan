---
title: "Task 1 - Setup Azure CloudShell"
chapter: true
weight: 2
---

### Task 1 - Setup your AzureCloud Shell
* Login to Azure Cloud Portal [https://portal.azure.com/](https://portal.azure.com/) with the provided login/password

    ![cloudshell1](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/cloudshell-01.jpg)
    ![cloudshell2](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/cloudshell-02.jpg)

* Click the link "Skip for now (14 days until this is required)" do not click the "Next" button

    ![cloudshell3](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/cloudshell-03.jpg)

* Click the "Next" button

    ![cloudshell4](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/cloudshell-04.jpg)

* Click on Cloud Shell icon on the Top Right side of the portal

    ![cloudshell5](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/cloudshell-05.jpg)

* Select **Bash**

    ![cloudshell6](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/cloudshell-06.jpg)

* Click on **Show advanced settings**

    ![cloudshell7](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/cloudshell-07.jpg)
* Select
  * Use existing Resource Group  - it ***should*** auto populate with USERXX-workshop-sdwan (USERXX is your Username)
  * Use existing Storage account - it ***should*** auto populate with USERXX########## (########## is a random string)
  * Use existing File Share  - type **cloudshellshare**
* Click "Attach Storage"

    ![cloudshell8](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/cloudshell-08.jpg)

* You should now have access to Azure Cloud Shell console

    ![cloudshell9](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/cloudshell-09.jpg)

### Task 2 - Run the Terraform Deployment

Perform the following step in your Cloudshell console to create your environment.

1. Clone the Github repo
1. Change directory to the `technical-recipe-azure-sdwan/terraform` folder
1. Run `terraform init`
1. Run `terraform plan` for your `username`
1. Run `terraform apply` for your `username`

> **Copy and paste these commands into your Cloud Shell console.**
> The terraform variable `username` will be populated with the value of the environment variable `USER`

```sh
git clone https://github.com/FortinetSecDevOps/technical-recipe-azure-sdwan
cd ./technical-recipe-azure-sdwan/terraform/
terraform init
terraform plan -var="username=${USER}"
terraform apply -var="username=${USER}" -auto-approve
```

  ![terraform1](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/terraform-01.jpg)
  ![terraform2](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/terraform-02.jpg)
  ![terraform3](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/terraform-03.jpg)

* At the end of this step you should have the following architecture

    ![global-step1](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/sdwan_architecture_01.jpg)

### Task 3 - Terraform Verification

  1. Using the Terraform output, verify that you have Web and SSH access to the FortiGates.

      ![terraform4](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/terraform-04.jpg)

      * Terraform output can be redisplayed at any point as long as you are in the `./technical-recipe-azure-sdwan/terraform/` directory, by using the command `terraform output`

        ```sh
        cd
        cd ./technical-recipe-azure-sdwan/terraform/
        terraform output
        ````

  1. Connect to the Branch FortiGates and check the VPN IPSec status.
  1. Connect to the Hub FortiGates and check the WAN IP

{{% notice warning %}}
<p style='text-align: left;'>
The examples and sample code provided in this workshop are intended to be consumed as instructional content. These will help you understand how various Fortinet and Azure services can be architected to build a solution while demonstrating best practices along the way. These examples are not intended for use in production environments without full understanding of how they operate.
</p>
{{% /notice %}}