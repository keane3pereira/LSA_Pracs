>---
> # **Practical 5**
> ##### Install Samba to share folder or files between Windows and Linux.
>---


> **Install the samba package**
```
sudo apt-get update
sudo apt-get install samba
```

> **Create a directory for it to share**
```
mkdir /home/kali/sambashare/
```

> **Created two files to test**

![shared_dir](https://raw.githubusercontent.com/keane3pereira/LSA_Pracs/master/res/samba/shared_dir.PNG)


> **The configuration file. Have to add the directory we want to share.**
```
sudo nano /etc/samba/smb.conf
```

> **Add this to the end of the file.**
```
[sambashare]
    comment = Samba on Ubuntu
    path = /home/username/sambashare
    read only = no
    browsable = yes
```

![smb_conf](https://raw.githubusercontent.com/keane3pereira/LSA_Pracs/master/res/samba/smb-conf.PNG)

> **Start/Restart the service**
```
sudo service smbd restart
```

> **Allow samba through the firewall**
```
sudo ufw allow samba
```

![service-ufw](res/samba/service-ufw.PNG)

> **Setting up User Account**
```
sudo smbpasswd -a kali
```
_**Note:** Username must belong to a system account._

![adduser](res/samba/adduser.PNG)

> **Open the file explorer, type  `smb://<ip-address>/<shared_file>`**
```
smb://127.0.0.1/sambashare
```

![smbdir](res/samba/smb-dir.PNG)
___