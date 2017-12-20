# Configuring MariaDB for Remote Client Access


**bind-address**

要注释掉

Loopback network device
NIC


:: every ip


**skip-networking**

tell MariaDB to run without any of the TCP/IP networking options





## Granting User Connections From Remote Hosts

`SELECT User, Host FROM mysql.user WHERE Host <> 'localhost';
`

list of allowed privileges
what database/tables these privileges apply to
username
host this user can connect from
and optionally a password



`GRANT ALL PRIVILEGES ON *.* TO 'root'@'192.168.100.%' IDENTIFIED BY 'my-new-password' WITH GRANT OPTION;`


关于grant

https://mariadb.com/kb/en/grant/


## Port 3306 is Configured in Firewall


CentOS 7 RHEL

```
firewall-cmd --add-port=3306/tcp 
firewall-cmd --permanent --add-port=3306/tcp
```



