##Comando terasort utilizado

time /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort -Dmapreduce.job.maps=4 -Dmapreduce.job.reduces=8 -Dmapreduce.map.memory.mb=8000 -Dmapreduce.reduce.memory.mb=8000 /user/saturn/teragen /user/saturn/terasort
