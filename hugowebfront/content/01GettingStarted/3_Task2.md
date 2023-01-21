---
title: "Task 2 - Run Terraform"
chapter: true
weight: 3
---

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

{{% notice warning %}}
The examples and sample code provided in this workshop are intended to be consumed as instructional content. These will help you understand how various Fortinet and Azure services can be architected to build a solution while demonstrating best practices along the way. These examples are not intended for use in production environments without full understanding of how they operate.
{{% /notice %}}
