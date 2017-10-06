##hostname of your database server

MariaDB [(none)]> show variables where Variable_name='hostname';
+---------------+------------------+
| Variable_name | Value            |
+---------------+------------------+
| hostname      | ip-172-31-35-152 |
+---------------+------------------+
1 row in set (0.00 sec)

##Version 

[root@ip-172-31-35-152 ec2-user]# mysql -V
mysql  Ver 15.1 Distrib 5.5.56-MariaDB, for Linux (x86_64) using readline 5.1

##Listado de bases de datos


MariaDB [(none)]> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| hive               |
| hue                |
| mysql              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
+--------------------+
8 rows in set (0.00 sec)

