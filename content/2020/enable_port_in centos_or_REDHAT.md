# Enable port in distribution Centos or Linux Red Had Enteprise

In this tutorial of how enable a port we going to do the example of change the port of the SSH service and we going to enable that new port in the firewall and in SELinux

For to do that changes of to enable the port in Centos or LRHE, we must follow the steps that describe the next:

- We modified the configuration file of service SSH and we modified the line that indique the port and we must changed the port by the port desired that in our case is 2248.

```
nano /etc/ssh/sshd_config

#port 22
port 2248
```

- When we already modified the configuration file, we must restar the service for to apply the changes that we apply in the file, if when the service is restart, we see a error message in the restart of service is because the firewall and the service of SELinux is blocked the new port indicated.

Restart of service.

```
systemctl restart sshd
```

Status of service.

```
[root@server ssh]# systemctl status sshd
● sshd.service - OpenSSH server daemon
   Loaded: loaded (/usr/lib/systemd/system/sshd.service; enabled; vendor preset: enabled)
   Active: active (running) since mar 2019-01-29 09:32:18 UTC; 3s ago
     Docs: man:sshd(8)
           man:sshd_config(5)
 Main PID: 20259 (sshd)
   CGroup: /system.slice/sshd.service
           └─20259 /usr/sbin/sshd -D

ene 29 09:32:17 server systemd[1]: Starting OpenSSH server daemon...
ene 29 09:32:18 server sshd[20259]: error: Bind to port 2248 on 0.0.0.0 failed: Permission denied.  <------------------- ERROR
ene 29 09:32:18 server sshd[20259]: error: Bind to port 2248 on :: failed: Permission denied.   	<------------------- ERROR
ene 29 09:32:18 server sshd[20259]: Server listening on 0.0.0.0 port 22.
ene 29 09:32:18 server sshd[20259]: Server listening on :: port 22.
ene 29 09:32:18 server systemd[1]: Started OpenSSH server daemon.
```

- For that the service can start correctly we must enable the ports that need the service, in our case is the port 2248 so for this we enable the port 2248 in the firewall.

Add firewall rule.

```
firewall-cmd --zone=trusted --add-port=2248/tcp --permanent
```

Restart firewall for to apply the changes.

```
firewall-cmd --reload
```

List rule added of firewall.

```
[root@server ssh]# firewall-cmd --list-all
trusted (active)
  target: ACCEPT
  icmp-block-inversion: no
  interfaces: eth0
  sources: 
  services: 
  ports: 2248/tcp
  protocols: 
  masquerade: no
  forward-ports: 
  sourceports: 
  icmp-blocks: 
  rich rules: 
```

- Once that the firewall rule is added, now we create the rule of SELinux for that the security system of SELinux permit the use of that port in the system correctly.

Add SELinux rule.

```
semanage port -a -t ssh_port_t -p tcp 2248
```

List rule added of SELinux.

```
[root@server ssh]# semanage port -l | grep ssh
ssh_port_t                     tcp      2248, 22
```

- When we already added the rule of SELinux, we must restart the service again for that already the service can use the port 2248 correctly.

Restart service.

```
[root@service ssh]# systemctl restart sshd.service
```

Status of service.

```
[root@service ssh]# systemctl status sshd.service
● sshd.service - OpenSSH server daemon
   Loaded: loaded (/usr/lib/systemd/system/sshd.service; enabled; vendor preset: enabled)
   Active: active (running) since mar 2019-01-29 09:41:15 UTC; 3s ago
     Docs: man:sshd(8)
           man:sshd_config(5)
 Main PID: 20399 (sshd)
   CGroup: /system.slice/sshd.service
           └─20399 /usr/sbin/sshd -D

ene 29 09:41:15 service systemd[1]: Starting OpenSSH server daemon...
ene 29 09:41:15 service sshd[20399]: Server listening on 0.0.0.0 port 2248.
ene 29 09:41:15 service sshd[20399]: Server listening on :: port 2248.
ene 29 09:41:15 service sshd[20399]: Server listening on 0.0.0.0 port 22.
ene 29 09:41:15 service systemd[1]: Started OpenSSH server daemon.
ene 29 09:41:15 service sshd[20399]: Server listening on :: port 22.
```

- In the moment that already restarted the service of ssh we can to use of ssh with de new port defined.
