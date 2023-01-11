---
title: "Task 2 - Run Terraform"
chapter: true
weight: 3
---

### Task 2 - Run the Terraform Code

Perform the following step in your Cloudshell console to create your environment.

1. Clone the Github repo
1. Change directory to the se-conf-sdwan-workshop/se-summit folder
1. Initialize Terraform
1. Create Terraform Plan
1. Apply Terraform Plan

> **Copy and paste these commands into your Cloudshell console.**
> The terraform variable `username` will be populated with the value of the environment variable `USER`

```sh
git clone https://github.com/FortinetSecDevOps/se-conf-sdwan-workshop.git
cd ./se-conf-sdwan-workshop/se-summit/
terraform init
terraform plan -var="username=${USER}"
terraform apply -var="username=${USER}"
```

  ![gitclone](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/git-clone.jpg)

* At the end of this step you should have the following architecture

    ![global-step1](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/sdwan_architecture_01.jpg)

{{% notice warning %}}
<p style='text-align: left;'>
The examples and sample code provided in this workshop are intended to be consumed as instructional content. These will help you understand how various Fortinet and Azure services can be architected to build a solution while demonstrating best practices along the way. These examples are not intended for use in production environments without full understanding of how they operate.
</p>
{{% /notice %}}