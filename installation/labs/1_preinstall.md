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



