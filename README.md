# Secure Small Office Network – Blue Team Lab

## Overview
This project is a hands-on blue team lab built using Cisco Packet Tracer. It simulates a small office network and focuses on defensive networking techniques such as network segmentation, access control, and basic hardening. The goal is to reduce the attack surface, prevent unauthorized access, and validate that security controls are working as intended.
---

## Network Design
The network has:
- 1 Cisco Router
- 1 Cisco Switch
- 3 PCs

To keep the network organized and secure, I separated the PCs into three VLANs:
- **VLAN 10 – Admin** 
- **VLAN 20 – Employee** 
- **VLAN 30 – Guest** 

Each VLAN has its own IP range and traffic is routed through the router so devices in different VLANs can communicate.

---

## What I Tried to Achieve
- Stop guest PCs from accessing admin PCs
- Let employees communicate with admin PCs
- Limit chances of attackers moving through the network
- Prevent unknown devices from connecting to the network

Basically, I wanted to practice **realistic defensive network skills** while keeping things simple.

---

## How I Did It

### VLAN Segmentation
I separated users into different VLANs to make sure that devices with less trust can’t access sensitive parts of the network.

### Router-on-a-Stick 
I created subinterfaces on the router for each VLAN so that traffic could flow between VLANs safely. Each subinterface has its own IP address as the default gateway.

### Access Control Lists (ACLs)
I made a simple ACL on the router to block Guest traffic from reaching Admin PCs while still letting normal traffic flow. This is one of the first defensive rules I learned to protect networks.

### Port Security
On the switch I enabled port security to allow only one device per port. If a wrong device connects the port shuts down. This prevents rogue devices from entering the network.


---

## Tools Used
- Cisco Packet Tracer  
- Cisco IOS CLI

---

## Files Included
- `secure-office-network.pkt` – The Packet Tracer lab file  
- `router-config.txt` – Router configuration I wrote  
- `switch-config.txt` – Switch configuration I wrote  

---

## What I Learned
- How VLANs and routing work in a small network  
- How ACLs can control traffic  
- How to use port security to block rogue devices  
- How to document a lab project for others to understand  

---

This lab was built using concepts from my **Cisco CCNA: Switching, Routing, and Wireless Essentials (SRWE)** course. It’s my first attempt at combining networking knowledge with practical blue team skills.
