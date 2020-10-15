>---
> # **Practical 6**
> ##### Configure NTP, install and configure NTP Server, Configure NTP Client.
>---

__NTP - Network Time Protocol__

The Network Time Protocol (NTP) is a networking protocol for clock synchronization between computer systems over packet-switched, variable-latency data networks. In operation since before 1985, NTP is one of the oldest Internet protocols in current use. NTP is intended to synchronize all participating computers to within a few milliseconds of Coordinated Universal Time (UTC).
NTP Port Number --> 123

> __Steps:__

- Update apt

```
sudo apt-get update
```

```
sudo apt update
```

- Install NTP

```
sudo apt-get install ntp
```

- Install SNTP

```
sudo apt-get install sntp
```

- Check the version of SNTP installed

```
sudo sntp --version
```

- Check if the ntp.conf file exists.

```
cd /etc
```

```
ls -lrth *ntp.conf
```

![ls](https://raw.githubusercontent.com/keane3pereira/LSA_Pracs/master/res/ntp/ls.PNG)

- Edit the config file

```
sudo nano /etc/ntp.conf
```

- Add the following line, save and exit

```
server localhost
```

![ntp.conf](https://raw.githubusercontent.com/keane3pereira/LSA_Pracs/master/res/ntp/ntp.conf.PNG)

- Start/Restart the service

```
sudo systemctl restart ntp
```

- Check the status of the service

```
sudo systemctl status ntp
```

- Query NTP to check the connection

```
sudo ntpq -p
```

![ntpq](https://raw.githubusercontent.com/keane3pereira/LSA_Pracs/master/res/ntp/ntpq.PNG)