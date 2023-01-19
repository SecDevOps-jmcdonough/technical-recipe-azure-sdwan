---
title: "Chapter 1 Quiz"
chapter: true
weight: 5
---

### Chapter 1 - QUIZ

1. FortiGates in the Hub do not have public IPs, how are they accessible via the Web UI?

1. Why are the VPN connections down?

  <details>
  <summary>Quiz 1 Answers</summary>

1. **FortiGates in the Hub do not have public IPs, how are they accessible via the Web UI?**

    * The Public IPs on the external load balancers for the Hub, Branch1 and Branch2 FortiGates have inbound NAT rules setup.

1. **Why are the VPN connections down?**

    * The external load balancer for the Hub FortiGates needs load balancing rules for UDP 500 and UDP 4500.

  </details>
</details>

***


    

{{% notice warning %}}
<p style='text-align: left;'>
The examples and sample code provided in this workshop are intended to be consumed as instructional content. These will help you understand how various Fortinet and Azure services can be architected to build a solution while demonstrating best practices along the way. These examples are not intended for use in production environments without full understanding of how they operate.
</p>
{{% /notice %}}