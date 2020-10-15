>---
> # **Practical 2**
> ##### Initial settings: Adding a User, Network Settings, Change to static IP address, Disable IPv6 if not needed, Configure Services, display the list of services which are running, Stop and turn OFF auto-start setting for a service if you don’t need it, Sudo Settings
>---

> **Adding a User**

- `adduser <username>` or `useradd <username>`
- To add a user to a group,
  `sudo adduser <username> <groupname>`


> **IP address**
- `ifconfig -a` or `ip address` or `ip a`

> **Change to static IP**
  - In the file `/etc/network/interfaces`
  Change dynamic to static wherever required
  - ```
    # /etc/network/interfaces

    # This file describes the network interfaces available on your system
    # and how to activate them. For more information, see interfaces(5).

    # The loopback network interface
    auto lo
    iface lo inet loopback

    # The primary network interface
    auto eth0
    iface eth0 inet static
        address 10.0.0.41
        netmask 255.255.255.0
        network 10.0.0.0
        broadcast 10.0.0.255
        gateway 10.0.0.1
        dns-nameservers 10.0.0.1 8.8.8.8
        dns-domain kali.com
        dns-search kali.com ```
  - Restart the network:
  `ifdown eth0` `ifup eth0`


> **Disabling IPv6**
- In the file `/etc/sysctl.conf`,
  Change the following lines:
- ```
  net.ipv6.conf.all.disable_ipv6 = 1
  net.ipv6.conf.default.disable_ipv6 = 1
  ```

> **Start, Stop, Restart services:**
  - `sudo systemctl start SERVICE_NAME`
  - `sudo systemctl stop SERVICE_NAME`
  - `sudo systemctl restart SERVICE_NAME`

> **List running services**
  - `sudo systemctl -t=service --state=running`

> **Installing packages**
  - `sudo apt-get install package-name`
---