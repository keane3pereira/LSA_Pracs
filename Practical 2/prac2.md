>---
> # **Practical 2**
> ##### Initial settings: Adding a User, Network Settings, Change to static IP address, Disable IPv6 if not needed, Configure Services, display the list of services which are running, Stop and turn OFF auto-start setting for a service if you don’t need it, Sudo Settings
>---

- Adding a User
`adduser <username>`

- IP address
  `ifconfig -a` or `ip address` or `ip a`

- Start, Stop, Restart services:
  `sudo systemctl start SERVICE_NAME`
  `sudo systemctl stop SERVICE_NAME`
  `sudo systemctl restart SERVICE_NAME`
  

- List running services
  `sudo systemctl -t=service --state=running`

- Installing packages
  `sudo apt install package-name`