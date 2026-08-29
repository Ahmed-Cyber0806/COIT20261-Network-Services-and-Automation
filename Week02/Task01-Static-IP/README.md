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

When reloading the configuration on Host3, the `ifdown eth0` command
reported that interface `eth0` was not configured. This occurred because
the interface had not previously been loaded from the interfaces file.
I then ran `ifup eth0`, which loaded the new configuration and assigned
`10.2.1.3/24` successfully.
Host4 was configured using the `ip address add` command. This setting is
temporary and must be entered again if the host is restarted.

## What I learned

I learned three methods of configuring static IPv4 addresses on Linux
hosts. Configuring an address through GNS3 before startup and editing
`/etc/network/interfaces` provide persistent configuration. In contrast,
the `ip address add` command applies the address immediately but does not
preserve it after a restart. I also used `ip address show` to verify that
all four hosts were configured on the same subnet.

## Submitted files

- `Setting-IP-12325506.gns3project.zip`
- `screenshots/Setting-IP-12325506-network.jpeg`
- `screenshots/Setting-IP-12325506-host1.jpeg`
- `screenshots/Setting-IP-12325506-host2.jpeg`
- `screenshots/Setting-IP-12325506-host3.jpeg`
- `screenshots/Setting-IP-12325506-host4.jpeg`
