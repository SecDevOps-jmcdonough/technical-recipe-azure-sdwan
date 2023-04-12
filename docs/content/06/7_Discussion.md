---
title: "Chapter 6 Discussion"
chapter: true
weight: 7
---

## ***Discussion Points During a Demo - Chapter 6***

In Active/Passive FortiGate deployments the failover methodology has an impact on the continuation of traffic flow. Utilizing Azure Load Balancers as traffic direction devices in a FortiGate Active/Passive deployment, the load balancer will only send traffic to the FortiGate that is responding to the load balancer's health probe. A FortiGate in passive mode will not respond to the load balancer health probe, causing the load balancer to mark the passive FortiGate as unhealthy and not send traffic to the passive FortiGate. In a failover event the previously passive FortiGate will start responding to the load balancer health probe, resulting in traffic being directed to the newly active FortiGate.

Azure load balancers do not maintain TCP sessions which will need to be restarted, however UDP sessions, specifically IPSEC connections are readily available in a failover scenario.

Reiterating, `ping` can be an effective way to determine reachability in the Cloud, however a `ping` may not fully exercise the services provided by the workloads. FortiGate policy should be set to allow/disallow service ports and protocols. In this section a loop utilizing curl to make http calls to a website was a better method to determine reachability in conjunction with functionality.

## Key questions during your demo - Chapter 6

* Is a highly available FortiGate deployment required for your workloads?
* Current Azure failover times for an Active/Passive deployment with load balancers is 5-10 seconds, can you applications support that?
* There are multiple tools to test system reachability adn service availability, what are your methods?

***
