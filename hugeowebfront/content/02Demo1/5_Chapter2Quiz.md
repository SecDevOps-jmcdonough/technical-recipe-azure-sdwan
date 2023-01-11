---
title: "Chapter 2 Quiz"
chapter: true
weight: 5
---

### Chapter 2 - QUIZ

1. Why is one FortiGate depicted as unhealthy by the Azure Hub External Load Balancer?

1. Why is NAT used to access the FortiGates, but for IPSEC VPN traffic Load balancing rules are used?

1. Do FortiGates in the Branches learn Spoke11 and Spoke12 CIDRs?

  <details>
  <summary>Quiz 2 Answers</summary>

1. **Why is one FortiGate depicted as unhealthy by the Azure Hub External Load Balancer?**

    * The passive FortiGate does not respond to the load balancer health probes. Only after a failover event will the newly active FortiGate start responding to health probes.

1. **Why is NAT used to access the FortiGates, but for IPSEC VPN traffic Load balancing rules are used?**

    * NAT allows each individual FortiGate to be accessed via the Public IP of the load balancer. A load balancer rule would only allow access to the Active FortiGate.

1. **Do FortiGates in the Branches learn Spoke11 and Spoke12 CIDRs?**

    * Spoke11 and Spoke12 CIDRs are not yet known to the Hub FortiGate so the Branches will not learn them yet.
