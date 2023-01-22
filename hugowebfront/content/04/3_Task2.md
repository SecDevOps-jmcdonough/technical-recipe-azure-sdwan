---
title: "Task 2 - LB Rules for VPN Traffic"
chapter: true
weight: 3
---

### Task 2 - Create load balancing rules for IPSEC VPN Traffic

1. **Select** the Hub External Load Balancer **sdwan-USERXX-workshop-hub1-elb1**
1. **Click** on Load balancing rules
1. **Click** "+ Add"
1. **Create** Load balancing rules for UDP 500 and UDP 4500 - ***one rule for each***
    * Name - `udp-500`
    * Name - `udp-4500`

    |Option|value||value
    |---|---|-|---|
    |Name|udp-500||udp-4500|
    |IP Version|IPv4||IPv4|
    |Frontend IP address|hub-pip1||hub-pip1|
    |Backend pool|hub1-ext-fgt||hub1-ext-fgt|
    |Protocol|UDP||UDP|
    |Port|500||4500|
    |Backend port|500||4500|
    |Health probe|hub1-elb1-probe||hub1-elb1-probe|
    |Session persistence|None||None|
    |Floating IP|Disabled||Disabled|
    |Outbound SNAT|Use implicit||Use implicit|

    ![hub-lb-rule1](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/externallbrule-01.jpg)
    ![hub-lb-rule2](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/externallbrule-02.jpg)
    ![hub-lb-rule3](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/externallbrule-03.jpg)
    ![hub-lb-rule4](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/externallbrule-04.jpg)
    ![hub-lb-rule5](https://raw.githubusercontent.com/FortinetSecDevOps/technical-recipe-azure-sdwan/main/images/externallbrule-05.jpg)
