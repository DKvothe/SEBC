-- Crear directorio 

[root@ip-172-31-28-197 ec2-user]# hdfs dfs -mkdir /precious

--subir archivo 

[root@ip-172-31-28-197 ec2-user]# hdfs dfs -copyFromLocal /home/ec2-user/SEBC-master-students.zip  /precious  

--Verificacion de archivos

[root@ip-172-31-28-197 ec2-user]# hdfs dfs -ls -h /precious
Found 1 items
-rw-r--r--   3 hdfs supergroup    464.5 K 2017-10-03 11:11 /precious/SEBC-master-students.zip


--Eliminad directorio no es posible al existir snapshot:

[root@ip-172-31-28-197 ec2-user]# hdfs dfs -rm -r /precious
rm: Failed to move to trash: hdfs://ip-172-31-26-66.us-east-2.compute.internal:8020/precious: The directory /precious cannot be deleted since /precious is snapshottable and already has snapshots

--Eliminar archivo zip:

[root@ip-172-31-28-197 ec2-user]# hdfs dfs -rm /precious/SEBC-master-students.zip
17/10/03 11:22:15 INFO fs.TrashPolicyDefault: Moved: 'hdfs://ip-172-31-26-66.us-east-2.compute.internal:8020/precious/SEBC-master-students.zip' to trash at: hdfs://ip-172-31-26-66.us-east-2.compute.internal:8020/user/hdfs/.Trash/Current/precious/SEBC-master-students.zip
