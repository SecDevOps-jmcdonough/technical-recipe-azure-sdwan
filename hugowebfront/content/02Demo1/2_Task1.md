---
title: "Task 1 - Add FortiGates to Hub LB"
chapter: true
weight: 2
---

### Task 1 - Add the FortiGates to the Hub Load Balancer Backend Pool

1. **Select** the Hub External Load Balancer **sdwan-USERXX-workshop-hub1-elb1**
1. **Click** Backend pools
1. **Select** "hub1-ext-fgt"
1. **Click** "+Add"
1. **Select** sdwan-USERXX-workshop-hub1-fgt1 and sdwan-USERXX-workshop-hub1-fgt2 **port1 interfaces**
    * 10.10.0.4
    * 10.10.0.5
1. **Click** "Add"
1. **Click** "Save"

  ![hub-lb-backend1](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/externallbbackend-01.jpg)
  ![hub-lb-backend2](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/externallbbackend-02.jpg)
  ![hub-lb-backend3](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/externallbbackend-03.jpg)
  ![hub-lb-backend4](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/externallbbackend-04.jpg)
  ![hub-lb-backend5](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/externallbbackend-05.jpg)
  ![hub-lb-backend6](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/externallbbackend-06.jpg)
  