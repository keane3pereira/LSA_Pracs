>---
> # **Practical 1**
> #### - Installation of DHCP Server in Ubuntu
>---

__DHCP: Dynamic Host Configuration Protocol__

A DHCP server is responsible for automatically providing, and assigning IP addresses, default gateways and other network parameters to client devices.

>Installation
- To install dhcp server on ubuntu:
`sudo apt-get install isc-dhcp-server`

- The server has to be configured based on the ip address. To check you ip address, the command is `ip address` or `ip a`
- You will also get info on the NIC card used. In this example we take `eth0`
- FOr example, we take IP address is `10.0.2.15`
---
- First we have to edit the default file that specifies the interfaces: `/etc/default/isc-dhcp-server`
- To edit, run `sudo nano /etc/default/isc-dhcp-server`
- Based on the interface you will need to change the following lines:
  `INTERFACESv4="eth0"`
- Save and exit the file. `Ctrl+X`, `Y`
---
- Next we have to change some settings in the configuration file at `/etc/dhcp/dhcpd.conf`
This will be changed based on your network configuration, i.e. IP aaddress, subnet mask, broadcast address, etc, based on your system.

```
# /etc/dhcp/dhcpd.conf

ddns-update-style none;
authoritative;

subnet 10.0.2.15 netmask 255.255.255.0 {
  range 10.0.2.1 10.0.2.254;
  option subnet-mask 255.255.255.0;
  option routers 10.0.2.255;
  option broadcast-address 10.0.2.255;
  default-lease 600;
  max-lease-time 7200;
}
```
- The remaining lines in the dhcpd.conf file will be commented.

---
- To start the dhcp service, run the following command:
  `sudo systemctl start isc-dhcp-server`

- To enable the service, run the command:
  `sudo systemctl enable isc-dhcp-server`