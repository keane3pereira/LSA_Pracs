>---
> # **Practical 4**
> ##### Configure DHCP (Dynamic Host Configuration Protocol) Server, Configure NFS Server to share directories on your Network, Configure NFS Client.
>---

> ### **Configuring the Server Machine**

> **Install NFS Kernel Server**

`sudo apt-get update`

`sudo apt install nfs-kernel-server`

> **Create the export directory**

`sudo mkdir -p /mnt/sharedfolder`

`sudo chown nobody:nogroup /mnt/sharedfolder`

`sudo chmod 777 /mnt/sharedfolder`

> **Adding a test file `a.txt` to test whether this works.**

![Image](https://raw.githubusercontent.com/keane3pereira/LSA_Pracs/master/res/prac4/atxt.PNG)

> **Assign server access to clients through the export file `/etc/exports`**
> 
> **A single client by adding the following line:
`/mnt/sharedfolder <client_ip>(rw,sync,no_subtree_check)`**

![Image](https://raw.githubusercontent.com/keane3pereira/LSA_Pracs/master/res/prac4/etcexports.PNG)

> **Export the shared directory**

`sudo exportfs -a`

> **Restart the service**

`sudo systemctl restart nfs-kernel-server`

> **Allow client through the firewall**

`sudo ufw allow from <client_ip> to any port nfs`

> **Check ufw status**
`sudo ufw status`

![Image](https://raw.githubusercontent.com/keane3pereira/LSA_Pracs/master/res/prac4/ufwstatus.PNG)

___

> ## **Configuring the Client machine:**

> **Update, the install nfs-common**

`sudo apt-get update`

`sudo apt-get install nfs-common`

> **Create a mount point for the host shared folder, to become accessible**

`sudo mkdir -p /mnt/sharedfolder_client`

> **Mount the shared directory on the Client using the command**
`sudo mount <server_ip>:<export_folder_server> </mnt/mountfolder_client>`

`sudo mount 127.0.0.1:/mnt/sharedfolder /mnt/sharedfolder_client`

> **The folder will now be accessible**

![Image](https://raw.githubusercontent.com/keane3pereira/LSA_Pracs/master/res/prac4/clientatxt.PNG)

___
