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

{{% notice warning %}}
The examples and sample code provided in this workshop are intended to be consumed as instructional content. These will help you understand how various Fortinet and Azure services can be architected to build a solution while demonstrating best practices along the way. These examples are not intended for use in production environments without full understanding of how they operate.
{{% /notice %}}
