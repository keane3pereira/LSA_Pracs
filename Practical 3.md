>---
> # **Practical 4**
> ##### SSH Server: Password Authentication Configure SSH Server to manage a server from the reomte computer, SSH Client.
>---


> **Install SSH**

`sudo apt-get install openssh-server`

> **Start the service**

`sudo systemctl start ssh`

> **Enable the service**

`sudo systemctl enable ssh`

> **Install UFW** _(This is the firewall package)_

`sudo apt-get install ufw`


> **Allow ssh through the firewall**

`sudo ufw allow ssh`

> **Enable the firewall**

`sudo ufw enable`

> **Check the status of the firewall**

`sudo ufw status`

> **Now you can test login**

`ssh kali@127.0.0.1`

![image](https://drive.google.com/uc?export=view&id=1cdgtPIayYE8Q-ChcQ3XbE7KtVWylI7s_)

> To configure the ssh, the file is located at `/etc/ssh/sshd_config`.
> 
> It contains options to configure the ssh. After configuring, restart the service, and your changes will be applied.

![image](https://drive.google.com/uc?export=view&id=1Sq49V4cf81OkOclq4qdV56XMc62TzNJw)
___