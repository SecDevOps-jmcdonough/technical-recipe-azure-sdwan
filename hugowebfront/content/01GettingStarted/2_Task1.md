---
title: "Task 1 Setup Azure CloudShell"
chapter: true
weight: 2
---

### Task 1 - Setup your AzureCloud Shell

* Login to Azure Cloud Portal [https://portal.azure.com/](https://portal.azure.com/) with the provided login/password

    ![cloudshell1](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/cloudshell-01.jpg)
    ![cloudshell2](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/cloudshell-02.jpg)

* Click on Cloud Shell icon on the Top Right side of the portal

    ![cloudshell4](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/cloudshell-04.jpg)

* Select **Bash**

    ![cloudshell5](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/cloudshell-05.jpg)

* Click on **Show advanced settings**

    ![cloudshell6]('https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/cloudshell-06.jpg')
* Select
  * Use existing Resource Group  - it ***should*** auto populate with USERXX-workshop-sdwan (USERXX is your Username)
  * Use existing Storage account - it ***should*** auto populate with USERXX##########workshopsdwa (########## is a random string)
  * Use existing File Share  - type **cloudshell**
* Click "Attach Storage"

    ![cloudshell7](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/cloudshell-07.jpg)

* You should now have access to Azure Cloud Shell console

    ![cloudshell8](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/cloudshell-08.jpg)

{{% notice warning %}}
<p style='text-align: left;'>
The examples and sample code provided in this workshop are intended to be consumed as instructional content. These will help you understand how various Fortinet and Azure services can be architected to build a solution while demonstrating best practices along the way. These examples are not intended for use in production environments without full understanding of how they operate.
</p>
{{% /notice %}}