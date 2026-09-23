# Enterprise Network Security Lab

## Objective

Designed and configured a small enterprise network using Cisco Packet Tracer, implementing VLAN segmentation, inter-VLAN routing, SSH-based secure management, and basic switch port security.

## Network Components

- 2 PCs
- 1 Cisco 2960 switch
- 1 Cisco 1941 router

## Networking Concepts Demonstrated

- VLAN segmentation
- Inter-VLAN routing
- Router-on-a-stick
- IPv4 addressing
- SSH secure management
- Local user authentication
- Switch port security
- Unused port isolation
- Network connectivity testing

## Network Topology

![Network Topology](topology.png)

## VLAN Configuration

### VLAN 10 — USERS

- **VLAN ID:** `10`
- **Name:** `USERS`
- **Network:** `192.168.10.0/24`
- **Gateway:** `192.168.10.1`
- **PC1:** `192.168.10.10`
- **SW1 Management:** `192.168.10.2`

### VLAN 20 — ADMIN

- **VLAN ID:** `20`
- **Name:** `ADMIN`
- **Network:** `192.168.20.0/24`
- **Gateway:** `192.168.20.1`
- **PC2:** `192.168.20.10`

### VLAN 999 — UNUSED

- **VLAN ID:** `999`
- **Name:** `UNUSED`
- **Purpose:** Unused switch ports are placed in this VLAN and administratively shut down.

## IP Addressing

- **R1 G0/0.10:** `192.168.10.1/24`
- **R1 G0/0.20:** `192.168.20.1/24`
- **SW1 VLAN 10:** `192.168.10.2/24`
- **PC1:** `192.168.10.10/24`
- **PC2:** `192.168.20.10/24`

## Router Configuration

R1 was configured using router-on-a-stick to provide inter-VLAN routing.

```text
interface gigabitEthernet 0/0.10
 encapsulation dot1Q 10
 ip address 192.168.10.1 255.255.255.0

interface gigabitEthernet 0/0.20
 encapsulation dot1Q 20
 ip address 192.168.20.1 255.255.255.0