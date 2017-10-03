--Creacion de directorio
[root@ip-172-31-26-66 hadoop-0.20-mapreduce]# export HADOOP_USER_NAME=hdfs
[root@ip-172-31-26-66 hadoop-0.20-mapreduce]# hdfs dfs -mkdir /user/DKvothe

--Ejecucion Teragen

[root@ip-172-31-26-66 hadoop-0.20-mapreduce]# hadoop jar hadoop-examples.jar teragen 5000000 /user/DKvothe
17/10/03 09:33:49 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-28-197.us-east-2.compute.internal/172.31.28.197:8032
17/10/03 09:33:50 INFO terasort.TeraGen: Generating 5000000 using 2
17/10/03 09:33:50 INFO mapreduce.JobSubmitter: number of splits:2
17/10/03 09:33:50 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1506998782120_0001
17/10/03 09:33:50 INFO impl.YarnClientImpl: Submitted application application_1506998782120_0001
17/10/03 09:33:50 INFO mapreduce.Job: The url to track the job: http://ip-172-31-28-197.us-east-2.compute.internal:8088/proxy/application_1506998782120_0001/
17/10/03 09:33:50 INFO mapreduce.Job: Running job: job_1506998782120_0001
17/10/03 09:33:56 INFO mapreduce.Job: Job job_1506998782120_0001 running in uber mode : false
17/10/03 09:33:56 INFO mapreduce.Job:  map 0% reduce 0%
17/10/03 09:34:05 INFO mapreduce.Job:  map 100% reduce 0%
17/10/03 09:34:06 INFO mapreduce.Job: Job job_1506998782120_0001 completed successfully
17/10/03 09:34:07 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=256074
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=167
                HDFS: Number of bytes written=500000000
                HDFS: Number of read operations=8
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=4
        Job Counters
                Launched map tasks=2
                Other local map tasks=2
                Total time spent by all maps in occupied slots (ms)=13867
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=13867
                Total vcore-milliseconds taken by all map tasks=13867
                Total megabyte-milliseconds taken by all map tasks=14199808
        Map-Reduce Framework
                Map input records=5000000
                Map output records=5000000
                Input split bytes=167
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=154
                CPU time spent (ms)=12960
                Physical memory (bytes) snapshot=740151296
                Virtual memory (bytes) snapshot=3208634368
                Total committed heap usage (bytes)=1213202432
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=10735710707299981
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=500000000

--Verificacion archivos

[root@ip-172-31-26-66 hadoop-0.20-mapreduce]# hdfs dfs -ls -h /user/DKvothe
Found 3 items
-rw-r--r--   3 hdfs supergroup          0 2017-10-03 09:34 /user/DKvothe/_SUCCESS
-rw-r--r--   3 hdfs supergroup    238.4 M 2017-10-03 09:34 /user/DKvothe/part-m-00000
-rw-r--r--   3 hdfs supergroup    238.4 M 2017-10-03 09:34 /user/DKvothe/part-m-00001

