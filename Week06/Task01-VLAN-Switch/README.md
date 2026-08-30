# Week 06 – Task 1: Setup VLANs on a Switch

## Student information

- **Student:** Ahmed Uddin Syed
- **Student ID:** 12325506
- **Unit code:** COIT20261
- **Tutor:** Mr Hossain
- **Campus:** Sydney
- **Date completed:** 30 August 2026

## Aim

The aim of this activity is to configure VLANs on an OpenvSwitch and
observe how VLAN membership separates hosts into different broadcast
domains.

## Project information

- **Project name:** Vlan-Basics-12325506
- **Switch:** OpenvSwitch
- **Hosts:** Four Linux Hosts
- **IPv4 network:** 10.6.1.0/24
- **VLAN IDs:** 506 and 507

## IP addressing and VLAN plan

| Host | IPv4 address | Switch port | VLAN |
|---|---|---|---|
| Host1 | 10.6.1.11/24 | eth1 | 506 |
| Host2 | 10.6.1.12/24 | eth2 | 506 |
| Host3 | 10.6.1.13/24 | eth3 | 507 |
| Host4 | 10.6.1.14/24 | eth4 | 507 |

Switch port `eth0` is unused in this task and reserved for the router in
Task 2.

## Switch configuration

```bash
ovs-vsctl set port eth1 tag=506
ovs-vsctl set port eth2 tag=506
ovs-vsctl set port eth3 tag=507
ovs-vsctl set port eth4 tag=507
ovs-vsctl show
```

## Connectivity observations

Before VLAN configuration, all four hosts were in the same Layer 2
network and could communicate.

After VLAN configuration:

- Host1 and Host2 could communicate because both were in VLAN 506.
- Host3 and Host4 could communicate because both were in VLAN 507.
- Hosts in VLAN 506 could not communicate with hosts in VLAN 507.
- A router is required for communication between the VLANs.

## Results and evidence

### Network topology

![VLAN topology](screenshots/Vlan-Basics-12325506-network.jpeg)

### OpenvSwitch ports and VLAN tags

![Switch ports](screenshots/Vlan-Basics-12325506-ports.jpeg)

### Connectivity before VLAN configuration

![Before VLANs](screenshots/Vlan-Basics-12325506-before-vlans.jpeg)

### Connectivity after VLAN configuration

![After VLANs](screenshots/Vlan-Basics-12325506-after-vlans.jpeg)

### ARP table

![ARP table](screenshots/Vlan-Basics-12325506-arp.jpeg)

## Problems and solutions

This section will be completed after the practical activity.

## What I learned

This section will be completed after the practical activity.

## Submitted files

- `Vlan-Basics-12325506.gns3project.zip`
- `screenshots/Vlan-Basics-12325506-network.jpeg`
- `screenshots/Vlan-Basics-12325506-ports.jpeg`
- `screenshots/Vlan-Basics-12325506-before-vlans.jpeg`
- `screenshots/Vlan-Basics-12325506-after-vlans.jpeg`
- `screenshots/Vlan-Basics-12325506-arp.jpeg`
