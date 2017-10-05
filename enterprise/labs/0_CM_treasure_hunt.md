What is ubertask optimization?

R: Activar la propiedad "Enable Ubertask Optimization mapreduce.job.ubertask.enable" en la configuración de YARN, permite que sea posible la mayor cantidad re tareas pequeñas denntro del cluster, esto depende de la configuración existente para los parametros:
mapreduce.job.ubertask.maxmaps, mapreduce.job.ubertask.maxreduces, mapreduce.job.ubertask.maxbytes 

Where in CM is the Kerberos Security Realm value displayed?

R: Se puede revisar verificando el parametro "Kerberos Security Realm default_realm", al cual se puede acceder siguiendo la ruta Administration > Settings > Kerberos

Se puede revisar verificando el parametro "Kerberos Security Realm default_realm", al cual se puede acceder siguiendo la ruta Administration > Settings > Kerberos

Which CDH service(s) host a property for enabling Kerberos authentication?

R: HDFS lo contiene, siguiendo la ruta : HDFS > Configuration  > Service-Wide > Security > Hadoop Secure Authentication 
 Se debe activar el check de Kerberos.
 
How do you upgrade the CM agents?

R: La actualizacion de los agentes puede ser realizadas de 2 formas, una es mediante ecloudera manager al realizar upgrade, aceptando la actualizacin de agentes:
Select Yes, I would like to upgrade the Cloudera Manager Agent packages now and click Continue.
  Tambien es posible realizarlo manualmente, indicando es el punto anterior quee no se desea realizar dicha actualización, en el caso de realizarlo manualmente es necesario tener actualizados los repositorios para la descarga de los agentes,
  Tras detener los agentes:
  service cloudera-scm-agent stop
  es posible proceder con la actualización:
  sudo yum clean all 
  sudo yum upgrade cloudera-manager-server cloudera-manager-daemons cloudera-manager-server-db-2 cloudera-manager-agent
  
Give the tsquery statement used to chart Hue's CPU utilization?

R: El grafico que viene por defecto, muestrra los ratios de uso de cpu por hue:

select cpu_system_rate + cpu_user_rate where category=ROLE and serviceName=hue

En caso de desear revisar el porcentaje de cpu utilizado por hue es posible con la siguiente consulta :

SELECT  cpu_percent WHERE category = ROLE AND serviceName = hue

Name all the roles that make up the Hive service

R: Los  roles que se crean con Hive so:

HiveServer2
Hive Metastore Server
Gateway

What steps must be completed before integrating Cloudera Manager with Kerberos?

R: Antes de realizar la integracion con cloudera y kerberos, es necesario contar con cloudera manager instalado,
gestionar la configuracion de kerberos de acuerdo al camino que se desea tomar, tener instalado los componentes de kerveros en el servidor y cliente correspondiente:
openldap-clients en el servidor
krb5-workstation, krb5-libs en todos los hosts.

Posteriormente tras contar con la configuración de kerberos correcta es posible realizar la activacion de kerberos desde cloudera manager indicando los valore con que se dispones, 
aportando la cuenta que realizara la creacion de los usuarios.
* Es necesario contar con los componentes de JCEP instalados, que permiten utilizar la seguridad a travez del cluster.

