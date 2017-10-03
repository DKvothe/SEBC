Cambiar swapp a 1:
echo 1 > /proc/sys/vm/swappiness
vi /etc/sysctl.conf

#agregue linea de configuracion 
vm.swappiness = 1

--Revision estado de unidades de disco
[root@ip-172-31-13-233 /]# cat /etc/fstab

#
# /etc/fstab
# Created by anaconda on Sun Jul 10 13:34:52 2016
#
# Accessible filesystems, by reference, are maintained under '/dev/disk'
# See man pages fstab(5), findfs(8), mount(8) and/or blkid(8) for more info
#
/dev/mapper/centos-root /       xfs     defaults        0 0
UUID=eee9894f-4e1f-49fb-9f5c-5ceddaa9a4cb /disco1 ext4 default 0 0
UUID=5cad11eb-3a36-46e8-9fcb-e37238d5b800 /disco2 ext4 default 0 0
UUID=8d6aa0ef-d963-4380-9748-2ed24a7c5c96       /boot   xfs     defaults        0 0

--Listado de espacios de disco

[root@ip-172-31-13-233 /]# lsblk
NAME            MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
xvda            202:0    0   40G  0 disk
├─xvda1         202:1    0  500M  0 part /boot
└─xvda2         202:2    0  7.5G  0 part
  ├─centos-root 253:0    0  6.7G  0 lvm  /
  └─centos-swap 253:1    0  820M  0 lvm
xvdb            202:16   0  120G  0 disk /disco1
xvdc            202:32   0  120G  0 disk /disco2

--Disable transparent hugepage support

echo 'never' > /sys/kernel/mm/transparent_hugepage/enabled
echo 'never' > /sys/kernel/mm/transparent_hugepage/defrag

# hacer configuracion permanente : Le agrego el valor al archivo 

vi  /etc/sysconfig/grub

transparent_hugepage=never

cat  /etc/sysconfig/grub
GRUB_TIMEOUT=30
GRUB_DISTRIBUTOR="$(sed 's, release .*$,,g' /etc/system-release)"
GRUB_DEFAULT=saved
GRUB_DISABLE_SUBMENU=true
GRUB_TERMINAL_OUTPUT="console"
GRUB_CMDLINE_LINUX="crashkernel=auto rd.lvm.lv=centos/root rd.lvm.lv=centos/swap rhgb quiet console=ttyS0 transparent_hugepage=never"
GRUB_DISABLE_RECOVERY="true"



--listar configuracion de red

ip link show
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN mode DEFAULT
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc pfifo_fast state UP mode DEFAULT qlen 1000
    link/ether 02:3a:64:6c:32:ee brd ff:ff:ff:ff:ff:ff
    
 ip addr show
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc pfifo_fast state UP qlen 1000
    link/ether 02:3a:64:6c:32:ee brd ff:ff:ff:ff:ff:ff
    inet 172.31.13.233/20 brd 172.31.15.255 scope global dynamic eth0
       valid_lft 2771sec preferred_lft 2771sec
    inet6 fe80::3a:64ff:fe6c:32ee/64 scope link
       valid_lft forever preferred_lft forever

--Host y DNS

getent hosts
127.0.0.1       localhost localhost.localdomain localhost4 localhost4.localdomain4
127.0.0.1       localhost localhost.localdomain localhost6 localhost6.localdomain6


--DNS
 nslookup ec2-18-221-223-153.us-east-2.compute.amazonaws.com
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
Name:   ec2-18-221-223-153.us-east-2.compute.amazonaws.com
Address: 172.31.1.21


--nscd


[root@ip-172-31-13-233 /]# service nscd status
Redirecting to /bin/systemctl status  nscd.service
● nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; enabled; vendor preset: disabled)
   Active: active (running) since Mon 2017-10-02 15:20:43 EDT; 1min 9s ago
 Main PID: 3638 (nscd)
   CGroup: /system.slice/nscd.service
           └─3638 /usr/sbin/nscd

Oct 02 15:20:43 ip-172-31-13-233 nscd[3638]: 3638 monitoring directory `/etc` (2)
Oct 02 15:20:43 ip-172-31-13-233 nscd[3638]: 3638 monitoring file `/etc/resolv.conf` (5)
Oct 02 15:20:43 ip-172-31-13-233 nscd[3638]: 3638 monitoring directory `/etc` (2)
Oct 02 15:20:43 ip-172-31-13-233 nscd[3638]: 3638 monitoring file `/etc/services` (6)
Oct 02 15:20:43 ip-172-31-13-233 nscd[3638]: 3638 monitoring directory `/etc` (2)
Oct 02 15:20:43 ip-172-31-13-233 nscd[3638]: 3638 disabled inotify-based monitoring for file `/etc/netgroup': No such file ...ectory
Oct 02 15:20:43 ip-172-31-13-233 nscd[3638]: 3638 stat failed for file `/etc/netgroup'; will try again later: No such file ...ectory
Oct 02 15:20:43 ip-172-31-13-233 nscd[3638]: 3638 Access Vector Cache (AVC) started
Oct 02 15:20:43 ip-172-31-13-233 systemd[1]: Started Name Service Cache Daemon.
Oct 02 15:21:02 ip-172-31-13-233 nscd[3638]: 3638 checking for monitored file `/etc/netgroup': No such file or directory
Hint: Some lines were ellipsized, use -l to show in full.


--ntpd
[root@ip-172-31-9-121 /]# service ntpd status
Redirecting to /bin/systemctl status  ntpd.service
● ntpd.service - Network Time Service
   Loaded: loaded (/usr/lib/systemd/system/ntpd.service; disabled; vendor preset: disabled)
   Active: active (running) since Mon 2017-10-02 15:28:14 EDT; 8s ago
  Process: 3200 ExecStart=/usr/sbin/ntpd -u ntp:ntp $OPTIONS (code=exited, status=0/SUCCESS)
 Main PID: 3201 (ntpd)
   CGroup: /system.slice/ntpd.service
           └─3201 /usr/sbin/ntpd -u ntp:ntp -g

Oct 02 15:28:14 ip-172-31-9-121 ntpd[3201]: Listen normally on 2 lo 127.0.0.1 UDP 123
Oct 02 15:28:14 ip-172-31-9-121 ntpd[3201]: Listen normally on 3 eth0 172.31.9.121 UDP 123
Oct 02 15:28:14 ip-172-31-9-121 ntpd[3201]: Listen normally on 4 lo ::1 UDP 123
Oct 02 15:28:14 ip-172-31-9-121 ntpd[3201]: Listen normally on 5 eth0 fe80::33:62ff:fe36:3df6 UDP 123
Oct 02 15:28:14 ip-172-31-9-121 ntpd[3201]: Listening on routing socket on fd #22 for interface updates
Oct 02 15:28:14 ip-172-31-9-121 systemd[1]: Started Network Time Service.
Oct 02 15:28:14 ip-172-31-9-121 ntpd[3201]: 0.0.0.0 c016 06 restart
Oct 02 15:28:14 ip-172-31-9-121 ntpd[3201]: 0.0.0.0 c012 02 freq_set kernel 0.000 PPM
Oct 02 15:28:14 ip-172-31-9-121 ntpd[3201]: 0.0.0.0 c011 01 freq_not_set
Oct 02 15:28:21 ip-172-31-9-121 ntpd[3201]: 0.0.0.0 c614 04 freq_mode


--instalacion base de datos
yum install mariadb-server 
mkdir -p /bkp/mariadb
mv /var/lib/mysql/ib_logfile0 /bkp/mariadb 
mv /var/lib/mysql/ib_logfile1 /bkp/mariadb

[root@ip-172-31-9-121 ec2-user]# systemctl list-unit-files | grep mariadb
mariadb.service                             enabled

--
Remove anonymous users? [Y/n] y
 ... Success!

Normally, root should only be allowed to connect from 'localhost'.  This
ensures that someone cannot guess at the root password from the network.

Disallow root login remotely? [Y/n] n
 ... skipping.

By default, MariaDB comes with a database named 'test' that anyone can
access.  This is also intended only for testing, and should be removed
before moving into a production environment.

Remove test database and access to it? [Y/n] y
 - Dropping test database...
 ... Success!
 - Removing privileges on test database...
 ... Success!

Reloading the privilege tables will ensure that all changes made so far
will take effect immediately.

Reload privilege tables now? [Y/n] y
 ... Success!

Cleaning up...

All done!  If you've completed all of the above steps, your MariaDB
installation should now be secure.

Thanks for using MariaDB!
--creacion bases de dato

MariaDB [(none)]> grant all on amon.* TO 'amon'@'%' IDENTIFIED BY 'amon_password';
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]> create database rman DEFAULT CHARACTER SET utf8;
Query OK, 1 row affected (0.00 sec)

MariaDB [(none)]> grant all on rman.* TO 'rman'@'%' IDENTIFIED BY 'rman_password';
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]> create database metastore DEFAULT CHARACTER SET utf8;
Query OK, 1 row affected (0.00 sec)

MariaDB [(none)]> grant all on metastore.* TO 'hive'@'%' IDENTIFIED BY 'hive_password';
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]> create database sentry DEFAULT CHARACTER SET utf8;
Query OK, 1 row affected (0.00 sec)

MariaDB [(none)]> grant all on sentry.* TO 'sentry'@'%' IDENTIFIED BY 'sentry_password';
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]> create database nav DEFAULT CHARACTER SET utf8;
Query OK, 1 row affected (0.00 sec)

MariaDB [(none)]> grant all on nav.* TO 'nav'@'%' IDENTIFIED BY 'nav_password';
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]> create database navms DEFAULT CHARACTER SET utf8;
Query OK, 1 row affected (0.00 sec)

MariaDB [(none)]> grant all on navms.* TO 'navms'@'%' IDENTIFIED BY 'navms_password';
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]> create database cmf DEFAULT CHARACTER SET utf8;
Query OK, 1 row affected (0.00 sec)

MariaDB [(none)]> grant all on cmf.* TO 'cmf'@'%' IDENTIFIED BY 'cmf_password';
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]> create database hue DEFAULT CHARACTER SET utf8;
Query OK, 1 row affected (0.00 sec)

MariaDB [(none)]> grant all on hue.* TO 'hue'@'%' IDENTIFIED BY 'hue_password';
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]> create database oozie DEFAULT CHARACTER SET utf8;
Query OK, 1 row affected (0.00 sec)

MariaDB [(none)]> grant all on oozie.* TO 'oozie'@'%' IDENTIFIED BY 'oozie_password';
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]> exit;

--Driver

[root@ip-172-31-9-121 /]# cd mysql-connector-java-5.1.44
[root@ip-172-31-9-121 mysql-connector-java-5.1.44]# ls
build.xml  CHANGES  COPYING  mysql-connector-java-5.1.44-bin.jar  README  README.txt  src
[root@ip-172-31-9-121 mysql-connector-java-5.1.44]# cp mysql-connector-java-5.1.44-bin.jar /usr/share/java/mysql-connector-java.jar
[root@ip-172-31-9-121 mysql-connector-java-5.1.44]#

--preparar base
[root@ip-172-31-9-121 /]# /usr/share/cmf/schema/scm_prepare_database.sh mysql cmf cmf cmf_password
JAVA_HOME=/opt/jdk1.8.0_131
Verifying that we can write to /etc/cloudera-scm-server
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /opt/jdk1.8.0_131/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/share/java/oracle-connector-java.jar:/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
[                          main] DbCommandExecutor              INFO  Successfully connected to database.
All done, your SCM database is configured correctly!
[root@ip-172-31-9-121 /]#

--Instalar JKD

cd /opt/
wget --no-cookies --no-check-certificate --header "Cookie: gpw_e24=http%3A%2F%2Fwww.oracle.com%2F; oraclelicense=accept-securebackup-cookie" "http://download.oracle.com/otn-pub/java/jdk/8u131-b11/d54c1d3a095b4ff2b6607d096fa80163/jdk-8u131-linux-x64.tar.gz"
tar xzf jdk-8u131-linux-x64.tar.gz

alternatives --install /usr/bin/java java /opt/jdk1.8.0_131/bin/java 2
alternatives --config java
 
There is 1 program that provides 'java'.
 
  Selection    Command
-----------------------------------------------
*+ 1           /opt/jdk1.8.0_131/bin/java
 
Enter to keep the current selection[+], or type selection number: 1


#Se inicia instalación de cloudera-scm-server y clodera-scm-agent


[root@ip-172-31-26-69 ec2-user]# service cloudera-scm-server status
● cloudera-scm-server.service - LSB: Cloudera SCM Server
   Loaded: loaded (/etc/rc.d/init.d/cloudera-scm-server; bad; vendor preset: disabled)
   Active: active (exited) since Mon 2017-10-02 22:21:24 EDT; 1h 3min ago
     Docs: man:systemd-sysv-generator(8)


[root@ip-172-31-26-66 ec2-user]# service cloudera-scm-agent status
● cloudera-scm-agent.service - LSB: Cloudera SCM Agent
   Loaded: loaded (/etc/rc.d/init.d/cloudera-scm-agent; bad; vendor preset: disabled)
   Active: active (exited) since Mon 2017-10-02 22:31:47 EDT; 54min ago
     Docs: man:systemd-sysv-generator(8)
  Process: 11676 ExecStart=/etc/rc.d/init.d/cloudera-scm-agent start (code=exited, status=0/SUCCESS)

Oct 02 22:31:46 ip-172-31-26-66 systemd[1]: Starting LSB: Cloudera SCM Agent...
Oct 02 22:31:46 ip-172-31-26-66 su[11689]: (to root) root on none
Oct 02 22:31:47 ip-172-31-26-66 cloudera-scm-agent[11676]: Starting cloudera-scm-agent: [  OK  ]
Oct 02 22:31:47 ip-172-31-26-66 systemd[1]: Started LSB: Cloudera SCM Agent.



