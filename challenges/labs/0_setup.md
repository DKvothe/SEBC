##cloud provider

AWS

##instances by IP address and DNS name privados

	  DNS														IP
-ip-172-31-35-27.us-east-2.compute.internal			  172.31.35.27
-ip-172-31-33-123.us-east-2.compute.internal			172.31.33.123
-ip-172-31-42-135.us-east-2.compute.internal			172.31.42.135
-ip-172-31-43-186.us-east-2.compute.internal			172.31.43.186
-ip-172-31-36-67.us-east-2.compute.internal			  172.31.36.67

##Linux release

Centos 7.2

##file system capacity

Filesystem               Size  Used Avail Use% Mounted on
/dev/mapper/centos-root  6.7G  1.3G  5.4G  20% /
devtmpfs                  16G     0   16G   0% /dev
tmpfs                     16G     0   16G   0% /dev/shm
tmpfs                     16G  8.4M   16G   1% /run
tmpfs                     16G     0   16G   0% /sys/fs/cgroup
/dev/xvdc                118G  140M  112G   1% /disco2
/dev/xvdb                118G   61M  112G   1% /disco1
/dev/xvda1               497M  140M  357M  29% /boot
tmpfs                    3.2G     0  3.2G   0% /run/user/1000

##Repositorios yum repolist enabled

[root@ip-172-31-42-135 ec2-user]# yum repolist enabled
Loaded plugins: fastestmirror
Loading mirror speeds from cached hostfile
 * base: centos.localmsp.org
 * extras: repos.dfw.quadranet.com
 * updates: repo.us.bigstepcloud.com
repo id                                                       repo name                                                      status
!base/7/x86_64                                                CentOS-7 - Base                                                9,591
!extras/7/x86_64                                              CentOS-7 - Extras                                                225
!updates/7/x86_64                                             CentOS-7 - Updates                                               731
repolist: 10,547


##Agregar usuarios y grupos 

adduser -u 2800 saturn
adduser -u 2900 haley
groupadd comets
groupadd planets
usermod -a -G comets haley
usermod -a -G planets saturn

##Usuarios

[root@ip-172-31-33-123 ec2-user]# cat /etc/passwd | grep 'saturn\|haley'
saturn:x:2800:2800::/home/saturn:/bin/bash
haley:x:2900:2900::/home/haley:/bin/bash

##Grupos

[root@ip-172-31-33-123 ec2-user]# cat /etc/group | grep 'comets\|planets'
comets:x:2901:haley
planets:x:2902:saturn







