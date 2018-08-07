---
 title: include file
 description: include file
 services: load balancer
 author: KumudD
 ms.service: load-balancer
 ms.topic: include
 ms.date: 7/26/2018
 ms.author: kumud
 ms.custom: include file
---

| | Standard SKU | Basic SKU |
| --- | --- | --- |
| Backend pool size | Supports up to 1000 instances | Supports up to 100 instances |
| Backend pool endpoints | Any virtual machine in a single virtual network, including blend of virtual machines, availability sets, virtual machine scale sets. | Virtual machines in a single availability set or virtual machine scale set. |
| Availability Zones | In Basic SKU, Zone-redundant and zonal frontends for inbound and outbound, outbound flows mappings survive zone failure, cross-zone load balancing. | n/a|
| Diagnostics | Azure Monitor, multi-dimensional metrics including byte and packet counters, health probe status, connection attempts (TCP SYN), outbound connection health (SNAT successful and failed flows), active data plane measurements | Azure Log Analytics for public Load Balancer only, SNAT exhaustion alert, backend pool health count. |
| HA Ports | Internal Load Balancer | n/a |
| Secure by default | Default closed for public IP and Load Balancer endpoints and a network security group must be used to explicitly whitelist for traffic to flow. | Default open, network security group optional. |
| [Outbound connections](../articles/load-balancer/load-balancer-outbound-connections.md) | Multiple frontends with per load balancing rule opt-out. An outbound scenario _must_ be explicitly created for the virtual machine to be able to use outbound connectivity.  Virtual Network Service Endpoints can be reached without outbound connectivity and do not count towards data processed.  Any public IP addresses, including Azure PaaS services not available as VNet Service Endpoints, must be reached via outbound connectivity and count towards data processed. When only an internal Load Balancer is serving a virtual machine, outbound connections via default SNAT are not available. Outbound SNAT programming is transport protocol specific based on protocol of the inbound load balancing rule. | Single frontend, selected at random when multiple frontends are present.  When only internal Load Balancer is serving a virtual machine, default SNAT is used. |
| [Multiple frontends](../articles/load-balancer/load-balancer-multivip-overview.md) | Inbound and [outbound](../articles/load-balancer/load-balancer-outbound-connections.md) | Inbound only |
| [Health probe down behavior](../articles/load-balancer/load-balancer-custom-probe-overview.md) | TCP connections stay alive on instance probe down __and__ on all probes down. | TCP connections stay alive on instance probe down. All TCP connections terminate on all probes down. |
| Management Operations | Most operations < 30 seconds | 60-90+ seconds typical. |
| SLA | 99.99% for data path with two healthy virtual machines. | Implicit in VM SLA. | 
| Pricing | Charged based on number of rules, data processed inbound or outbound associated with resource.  | No charge |
|  |  |  |