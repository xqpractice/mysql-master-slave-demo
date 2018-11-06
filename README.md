# mysql-master-slave-demo
Mysql Master-Slave Demo


## Init sql in master

```sql
GRANT REPLICATION SLAVE ON *.* TO 'master'@'ip-address' IDENTIFIED BY 'master';

FLUSH PRIVILEGES;

SHOW MASTER STATUS;
```


## Init sql in slave

```sql
CHANGE MASTER TO master_host='mysql-master', master_port=3306, master_user='master', master_password='master', master_log_file='mysql-bin.000003', master_log_pos=1293;

START SLAVE;

SHOW SLAVE STATUS;
```
