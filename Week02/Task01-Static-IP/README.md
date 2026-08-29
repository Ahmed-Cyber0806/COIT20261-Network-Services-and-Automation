# Week 02 – Task 1: Setting Static IP Addresses

## Student information

- **Student:** Ahmed Uddin Syed
- **Student ID:** 12325506
- **Unit code:** COIT20261
- **Tutor:** Mr Hossain
- **Campus:** Sydney
- **Date completed:** 29 August 2026

## Aim

The aim of this activity is to configure static IPv4 addresses on Linux
hosts using three different methods: the GNS3 configuration interface,
the `/etc/network/interfaces` file from the Linux console and the
`ip address add` command.

## Project information

- **Project name:** Setting-IP-12325506
- **Network:** 10.2.1.0/24
- **Subnet mask:** 255.255.255.0
- **Devices:** Four Linux Hosts and one Ethernet switch

## IP addressing table

| Device | IPv4 address | Configuration method |
|---|---|---|
| Host1 | 10.2.1.1/24 | GNS3 Configure menu |
| Host2 | 10.2.1.2/24 | GNS3 Configure menu |
| Host3 | 10.2.1.3/24 | `/etc/network/interfaces` from console |
| Host4 | 10.2.1.4/24 | `ip address add` command |

## Network configuration

Host1 and Host2 use a persistent static configuration similar to:

```text
auto eth0
iface eth0 inet static
    address DEVICE_IP_ADDRESS
    netmask 255.255.255.0
    up sysctl net.ipv4.ip_forward=0
```

Host3 is configured by editing `/etc/network/interfaces` after the node
has started and reloading the interface.

Host4 is configured temporarily with the `ip address add` command.

## Commands used

### Host3

```bash
nano /etc/network/interfaces
ifdown eth0
ifup eth0
ip address show
```

### Host4

```bash
ip address add 10.2.1.4/24 dev eth0
ip address show
```

## Results and evidence

### Network topology

![Static IP network](screenshots/Setting-IP-12325506-network.png)

The topology contains four Linux Hosts connected to one Ethernet switch
on the `10.2.1.0/24` network.

### Host1 IP address

![Host1 IP address](screenshots/Setting-IP-12325506-host1.png)

Host1 was configured through the GNS3 Configure menu.

### Host2 IP address

![Host2 IP address](screenshots/Setting-IP-12325506-host2.png)

Host2 was configured through the GNS3 Configure menu.

### Host3 IP address

![Host3 IP address](screenshots/Setting-IP-12325506-host3.png)

Host3 was configured by editing `/etc/network/interfaces` from its
console and reloading `eth0`.

### Host4 IP address

![Host4 IP address](screenshots/Setting-IP-12325506-host4.png)

Host4 was configured temporarily using the `ip address add` command.

## Problems and solutions

This section will be completed after the practical activity.

## What I learned

This section will be completed after the practical activity.

## Submitted files

- `Setting-IP-12325506.gns3project.zip`
- `screenshots/Setting-IP-12325506-network.png`
- `screenshots/Setting-IP-12325506-host1.png`
- `screenshots/Setting-IP-12325506-host2.png`
- `screenshots/Setting-IP-12325506-host3.png`
- `screenshots/Setting-IP-12325506-host4.png`
