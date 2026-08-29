# Week 01 – Task 1: Introduction to GNS3 Basics

## Student information

- **Student:** Ahmed Uddin Syed
- **Student ID:** 12325506
- **Unit code:** COIT20261
- **Tutor:** Mr Hossain
- **Campus:** Sydney
- **Date completed:** 29 August 2026

## Aim

The aim of this task is to become familiar with GNS3 by creating a
project, adding a Linux host, configuring a static IPv4 address and
checking the address from the Linux console.

## Project information

- **Project name:** GNS3-Intro-12325506
- **Node:** One Linux Host
- **Interface:** eth0
- **IPv4 address:** 10.10.1.1
- **Prefix length:** /24
- **Subnet mask:** 255.255.255.0
- **Network address:** 10.10.1.0/24

## Activities

1. Create a new GNS3 project named `GNS3-Intro-12325506`.
2. Add one Linux Host to the project.
3. Add a project annotation containing my student information.
4. Configure the Linux Host with the static address `10.10.1.1/24`.
5. Disable IP forwarding because this device operates as a host.
6. Start the Linux Host and open its console.
7. Use `ip address show` to verify the address.
8. Export the completed GNS3 project.

## Network configuration

The following configuration is used in `/etc/network/interfaces`:

```text
auto eth0
iface eth0 inet static
    address 10.10.1.1
    netmask 255.255.255.0
    up sysctl net.ipv4.ip_forward=0
```

A default gateway is not required because this activity contains only
one host and no router.

## Commands used

```bash
ip address show
```

## Results and evidence

### Network topology

![GNS3 network topology](screenshots/GNS3-Intro-12325506-network.png)

The network topology contains one Linux Host configured with the address
`10.10.1.1/24`. The project annotation identifies the activity and
includes my student information.

### IP address verification

![IP address verification](screenshots/GNS3-Intro-12325506-ipaddress.png)

The console output confirms that `10.10.1.1/24` is assigned to interface
`eth0`.

## Problems and solutions

This section will be completed after the practical activity.

## What I learned

This section will be completed after the practical activity.

## Submitted files

- `GNS3-Intro-12325506.gns3project`
- `screenshots/GNS3-Intro-12325506-network.png`
- `screenshots/GNS3-Intro-12325506-ipaddress.png`
