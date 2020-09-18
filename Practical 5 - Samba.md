>---
> # **Practical 5**
> ##### Install Samba to share folder or files between Windows and Linux.
>---


- **Install the samba package**
```
sudo apt-get update
sudo apt-get install samba
```

- **Create a directory for it to share**
```
mkdir /home/kali/sambashare/
```

- **Created two files to test**

![Image](https://raw.githubusercontent.com/keane3pereira/LSA_Pracs/master/res/prac5/shared_dir.PNG)


- **The configuration file. Have to add the directory we want to share.**
```
sudo nano /etc/samba/smb.conf
```

- **Add this to the end of the file.**
```
[sambashare]
    comment = Samba on Ubuntu
    path = /home/username/sambashare
    read only = no
    browsable = yes
```

![Image](https://raw.githubusercontent.com/keane3pereira/LSA_Pracs/master/res/prac5/smb-conf.PNG)

- **Start/Restart the service**
```
sudo service smbd restart
```

- **Allow samba through the firewall**
```
sudo ufw allow samba
```

![Image](https://raw.githubusercontent.com/keane3pereira/LSA_Pracs/master/res/prac5/service-ufw.PNG)

- **Setting up User Account**
```
sudo smbpasswd -a kali
```
_**Note:** Username must belong to a system account._

![Image](https://raw.githubusercontent.com/keane3pereira/LSA_Pracs/master/res/prac5/adduser.PNG)

- **Open the file explorer, type  `smb://<ip-address>/<shared_file>`**
```
smd://127.0.0.1/sambashare
```

![Image](https://raw.githubusercontent.com/keane3pereira/LSA_Pracs/master/res/prac5/smb-dir.PNG)