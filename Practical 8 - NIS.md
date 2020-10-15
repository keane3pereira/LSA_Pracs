>---
> # **Practical 8**
> ##### Configure NIS Server in order to share user accounts in your local network.
>---

```
sudo apt-get update
```

```
sudo apt update
```

```
sudo apt-get install nis
```

```
sudo nano /etc/default/nis
```

At one time pc can be either server or client
For demo, same step twice.

2 types of servers: master & slave(secondary server)

---
## SERVER
---

Set `NISSERVER=master` and `NISCLIENT=false`

Copying the config because we need to configure the client nis

```
sudo cp /etc/default/nis /etc/default/nis_client
```

Share anything that has columns. NIS has components, we will know 3.

-- ypserv: yellow pages (directory). It's a server where a client can query to see what service is there.

-- ypbind : Client binds tools

-- ypxfrd : NIS database is with master, this command sends the database to the slave (secondary server) for load balancing

(auth the user - settings, from IP : server side)

```
sudo nano /etc/ypserv.securenets
```
(edit accordingly)

- Find your IP using `ip a`

- Initialize yellow pages (build database)

```
sudo /usr/lib/yp/ypinit -m
```
Keep domain name / host name as kali.com

- Install make
```
sudo apt-get install make
```

```
sudo /usr/lib/yp/ypinit -m
```
- Check the service status
```
sudo systemctl status ypserv
```
- Start the service
```
sudo systemctl start ypserv
```

- Error - Failed to send 'clear' .... 

- Restart service rpcbind

```
sudo systemctl restart rpcbind nis
```

- Check status of rpcbind

```
sudo systemctl status rpcbind
```
If status is `active`, then great!

```
sudo /usr/lib/yp/ypinit -m
```

This should show `Updating...`

- Now add a user

```
sudo adduser kali psswd: kali
```

Now this adds user to NIS. This is the server-side config
```
cd /var/yp sudo make
```

---
## CLIENT
---

Client will try to resolve the server. Needs to be done on client only.

```
sudo nano /etc/hosts
```

Need to add ip of client and server
(client usually there)

On the client machine, update apt, and install nis. Domain name on client has to be same as server one.

- ypbind for client
```
sudo nano /etc/yp.conf
```

_............ (to be continued)_