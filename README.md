# packet_tracer_eigrp_routing

## Overview
Configuration of EIGRP (Enhanced Interior Gateway Routing Protocol) as a dynamic routing protocol between two routers, allowing them to automatically discover and advertise routes using a hybrid approach combining elements of both distance-vector and link-state protocols.

## Topology
Reference:
![Description](images/Routing+Diagram.jpg)
Result:
![Description](images/Screenshot.png)

Two routers (Router-1 and Router-2) connected together.

- Router-1: 192.168.10.1/24 (LAN), 192.168.20.1/24 (point-to-point link to Router-2)
- Router-2: 192.168.30.1/24 (LAN), 192.168.20.2/24 (point-to-point link to Router-1)

## Configuration
Configured EIGRP on both routers using number 10.

- Router-1:
    - router eigrp 10
    - network 192.168.10.0
    - network 192.168.20.0

- Router-2:
    - router eigrp 10
    - network 192.168.20.0 0.0.0.255
    - network 192.168.30.0 0.0.0.255

## Issues / Troubleshooting
Verified EIGRP neighbor adjacency and route advertisement using 'show ip route' to confirm routers had formed a neighbor relationship and learned each other's networks.

## What This Demonstrates
Understanding of EIGRP as a hybrid routing protocol, including configuration, autonomous system assignment, and neighbor verification. Unlike OSPF which uses cost based on bandwidth, EIGRP uses a composite metric incorporating bandwidth and delay by default.