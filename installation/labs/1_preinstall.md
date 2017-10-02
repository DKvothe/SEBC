Cambiar swapp a 1:
echo 1 > /proc/sys/vm/swappiness
vi /etc/sysctl.conf

#agregue linea de configuracion 
vm.swappiness = 1
