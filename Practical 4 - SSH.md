>---
> # **Practical 3**
> ##### SSH Server: Password Authentication Configure SSH Server to manage a server from the remote computer, SSH Client.
>---

> **Install SSH**
```
sudo apt-get install openssh-server
```

> **Start the service**
```
sudo systemctl start ssh
```

> **Enable the service**
```
sudo systemctl enable ssh
```

> **Install UFW** _(This is the firewall package)_
```
sudo apt-get install ufw
```


> **Allow ssh through the firewall**
```
sudo ufw allow ssh
```

> **Enable the firewall**
```
sudo ufw enable
```

> **Check the status of the firewall**
```
sudo ufw status
```

> **Now you can test login**
```
ssh kali@127.0.0.1
```


![testssh](https://raw.githubusercontent.com/keane3pereira/LSA_Pracs/master/res/ssh/test_ssh.PNG)

> **To configure the ssh, the file is located at `/etc/ssh/sshd_config`
> It contains options to configure the ssh. After configuring, restart the service, and your changes will be applied.**

![config](https://raw.githubusercontent.com/keane3pereira/LSA_Pracs/master/res/ssh/config.PNG)

___
