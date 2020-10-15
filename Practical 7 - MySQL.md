>---
> # **Practical 7**
> ##### Install MySQL to configure the Database Server
>---

MySQL is a freely available open source Relational Database Management System (RDBMS) that uses Structured Query Language (SQL). MySQL is free and open-source software under the terms of the GNU General Public License, and is also available under a variety of proprietary licenses. MySQL has stand-alone clients that allow users to interact directly with a MySQL database using SQL, but more often MySQL is used with other programs to implement applications that need relational database capability. MySQL is a component of the LAMP web application software stack

Default Port --> 3306

> **Steps:**

- Update apt

```
sudo apt-get update
```

- Install wget

```
sudo apt-get install wget
```

- Use wget to download the debian package for mysql
```

wget https://dev.mysql.com/get/mysql-apt-config_0.8.15-1_all.deb
```

![wget](https://raw.githubusercontent.com/keane3pereira/LSA_Pracs/master/res/mysql/wget.png)

- Install the downloaded package

```
sudo dpkg -i mysql-apt-config_0.8.15-1_all.deb
```

![bionic](https://raw.githubusercontent.com/keane3pereira/LSA_Pracs/master/res/mysql/bionic.png)

![ok](https://raw.githubusercontent.com/keane3pereira/LSA_Pracs/master/res/mysql/ok.png)

![dpkg](https://raw.githubusercontent.com/keane3pereira/LSA_Pracs/master/res/mysql/dpkg.png)

- Update apt again

```
sudo apt-get update
```

- Install `mysql-community-server`

```
sudo apt-get install mysql-community-server
```

![ok2](https://raw.githubusercontent.com/keane3pereira/LSA_Pracs/master/res/mysql/ok2.png)

![passwd](https://raw.githubusercontent.com/keane3pereira/LSA_Pracs/master/res/mysql/root.png)

- Enable and start the service

```
sudo systemctl enable mysql
```

```
sudo systemctl start mysql
```

Check the status of the service
```
sudo systemctl status mysql
```

![status](https://raw.githubusercontent.com/keane3pereira/LSA_Pracs/master/res/mysql/status.png)

- Log in to mysql

```
sudo mysql -u root -p
```