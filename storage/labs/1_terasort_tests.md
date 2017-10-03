--Creacion de usuario

useradd -g 0 -u 10001 DKvothe

--asignar password 

[root@ip-172-31-26-66 hadoop-0.20-mapreduce]# passwd DKvothe
Changing password for user DKvothe.
New password:
BAD PASSWORD: The password is shorter than 8 characters
Retype new password:
passwd: all authentication tokens updated successfully.

--verificacion usuario

DKvothe:x:10001:0::/home/DKvothe:/bin/bash
[root@ip-172-31-26-66 hadoop-0.20-mapreduce]#


--Crear directorio en hdfs

hdfs dfs -mkdir /user/DKvothe

--asignar directorio a usuario

[root@ip-172-31-28-197 ec2-user]# export HADOOP_USER_NAME=hdfs
[root@ip-172-31-28-197 ec2-user]# hdfs dfs -chown DKvothe /user/DKvothe
[root@ip-172-31-28-197 ec2-user]# hdfs dfs -ls /user
Found 3 items
drwxr-xr-x   - DKvothe supergroup          0 2017-10-03 09:34 /user/DKvothe
drwx------   - hdfs    supergroup          0 2017-10-03 09:33 /user/hdfs
drwxrwxrwx   - mapred  hadoop              0 2017-10-02 22:46 /user/history

--Creacion de 10GB con teragen


[root@ip-172-31-26-66 hadoop-0.20-mapreduce]# time hadoop jar hadoop-examples.jar teragen -Dmapred.map.tasks=4 -Ddfs.block.size=33554432 100000000  /user/DKvothe/teragen
17/10/03 10:42:33 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-28-197.us-east-2.compute.internal/172.31.28.197:8032
17/10/03 10:42:33 INFO terasort.TeraGen: Generating 100000000 using 4
17/10/03 10:42:33 INFO mapreduce.JobSubmitter: number of splits:4
17/10/03 10:42:33 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/10/03 10:42:33 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
17/10/03 10:42:33 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1506998782120_0002
17/10/03 10:42:33 INFO impl.YarnClientImpl: Submitted application application_1506998782120_0002
17/10/03 10:42:34 INFO mapreduce.Job: The url to track the job: http://ip-172-31-28-197.us-east-2.compute.internal:8088/proxy/application_1506998782120_0002/
17/10/03 10:42:34 INFO mapreduce.Job: Running job: job_1506998782120_0002
17/10/03 10:42:40 INFO mapreduce.Job: Job job_1506998782120_0002 running in uber mode : false
17/10/03 10:42:40 INFO mapreduce.Job:  map 0% reduce 0%
17/10/03 10:42:58 INFO mapreduce.Job:  map 15% reduce 0%
17/10/03 10:43:04 INFO mapreduce.Job:  map 23% reduce 0%
17/10/03 10:43:10 INFO mapreduce.Job:  map 30% reduce 0%
17/10/03 10:43:16 INFO mapreduce.Job:  map 32% reduce 0%
17/10/03 10:43:22 INFO mapreduce.Job:  map 33% reduce 0%
17/10/03 10:43:34 INFO mapreduce.Job:  map 40% reduce 0%
17/10/03 10:43:40 INFO mapreduce.Job:  map 47% reduce 0%
17/10/03 10:43:46 INFO mapreduce.Job:  map 52% reduce 0%
17/10/03 10:43:52 INFO mapreduce.Job:  map 60% reduce 0%
17/10/03 10:43:58 INFO mapreduce.Job:  map 61% reduce 0%
17/10/03 10:44:04 INFO mapreduce.Job:  map 65% reduce 0%
17/10/03 10:44:10 INFO mapreduce.Job:  map 71% reduce 0%
17/10/03 10:44:16 INFO mapreduce.Job:  map 78% reduce 0%
17/10/03 10:44:22 INFO mapreduce.Job:  map 80% reduce 0%
17/10/03 10:44:28 INFO mapreduce.Job:  map 85% reduce 0%
17/10/03 10:44:34 INFO mapreduce.Job:  map 93% reduce 0%
17/10/03 10:44:40 INFO mapreduce.Job:  map 98% reduce 0%
17/10/03 10:44:47 INFO mapreduce.Job:  map 100% reduce 0%
17/10/03 10:44:53 INFO mapreduce.Job: Job job_1506998782120_0002 completed successfully
17/10/03 10:44:53 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=512184
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=344
                HDFS: Number of bytes written=10000000000
                HDFS: Number of read operations=16
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=8
        Job Counters
                Launched map tasks=4
                Other local map tasks=4
                Total time spent by all maps in occupied slots (ms)=499157
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=499157
                Total vcore-milliseconds taken by all map tasks=499157
                Total megabyte-milliseconds taken by all map tasks=511136768
        Map-Reduce Framework
                Map input records=100000000
                Map output records=100000000
                Input split bytes=344
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=1376
                CPU time spent (ms)=148190
                Physical memory (bytes) snapshot=744185856
                Virtual memory (bytes) snapshot=6395052032
                Total committed heap usage (bytes)=1671430144
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=214760662691937609
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=10000000000

real    2m22.183s
user    0m4.851s
sys     0m0.255s


--Verificacion archivos

[root@ip-172-31-26-66 hadoop-0.20-mapreduce]# hdfs dfs -ls -h /user/DKvothe/teragen
Found 5 items
-rw-r--r--   3 hdfs supergroup          0 2017-10-03 10:44 /user/DKvothe/teragen/_SUCCESS
-rw-r--r--   3 hdfs supergroup      2.3 G 2017-10-03 10:44 /user/DKvothe/teragen/part-m-00000
-rw-r--r--   3 hdfs supergroup      2.3 G 2017-10-03 10:44 /user/DKvothe/teragen/part-m-00001
-rw-r--r--   3 hdfs supergroup      2.3 G 2017-10-03 10:44 /user/DKvothe/teragen/part-m-00002
-rw-r--r--   3 hdfs supergroup      2.3 G 2017-10-03 10:44 /user/DKvothe/teragen/part-m-00003

--Ejecucion Terasort

[root@ip-172-31-26-66 hadoop-0.20-mapreduce]# time hadoop jar hadoop-examples.jar terasort /user/DKvothe/teragen /user/DKvothe/terasort
17/10/03 10:49:40 INFO terasort.TeraSort: starting
17/10/03 10:49:42 INFO input.FileInputFormat: Total input paths to process : 4
Spent 223ms computing base-splits.
Spent 5ms computing TeraScheduler splits.
Computing input splits took 229ms
Sampling 10 splits of 300
Making 16 from 100000 sampled records
Computing parititions took 627ms
Spent 858ms computing partitions.
17/10/03 10:49:42 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-28-197.us-east-2.compute.internal/172.31.28.197:8032
17/10/03 10:49:43 INFO mapreduce.JobSubmitter: number of splits:300
17/10/03 10:49:43 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1506998782120_0003
17/10/03 10:49:43 INFO impl.YarnClientImpl: Submitted application application_1506998782120_0003
17/10/03 10:49:43 INFO mapreduce.Job: The url to track the job: http://ip-172-31-28-197.us-east-2.compute.internal:8088/proxy/application_1506998782120_0003/
17/10/03 10:49:43 INFO mapreduce.Job: Running job: job_1506998782120_0003
17/10/03 10:49:48 INFO mapreduce.Job: Job job_1506998782120_0003 running in uber mode : false
17/10/03 10:49:48 INFO mapreduce.Job:  map 0% reduce 0%
17/10/03 10:50:00 INFO mapreduce.Job:  map 1% reduce 0%
17/10/03 10:50:01 INFO mapreduce.Job:  map 2% reduce 0%
17/10/03 10:50:02 INFO mapreduce.Job:  map 5% reduce 0%
17/10/03 10:50:03 INFO mapreduce.Job:  map 9% reduce 0%
17/10/03 10:50:04 INFO mapreduce.Job:  map 10% reduce 0%
17/10/03 10:50:09 INFO mapreduce.Job:  map 11% reduce 0%
17/10/03 10:50:11 INFO mapreduce.Job:  map 12% reduce 0%
17/10/03 10:50:12 INFO mapreduce.Job:  map 13% reduce 0%
17/10/03 10:50:13 INFO mapreduce.Job:  map 14% reduce 0%
17/10/03 10:50:14 INFO mapreduce.Job:  map 16% reduce 0%
17/10/03 10:50:15 INFO mapreduce.Job:  map 20% reduce 0%
17/10/03 10:50:16 INFO mapreduce.Job:  map 21% reduce 0%
17/10/03 10:50:20 INFO mapreduce.Job:  map 22% reduce 0%
17/10/03 10:50:21 INFO mapreduce.Job:  map 23% reduce 0%
17/10/03 10:50:25 INFO mapreduce.Job:  map 24% reduce 0%
17/10/03 10:50:26 INFO mapreduce.Job:  map 25% reduce 0%
17/10/03 10:50:27 INFO mapreduce.Job:  map 28% reduce 0%
17/10/03 10:50:28 INFO mapreduce.Job:  map 31% reduce 0%
17/10/03 10:50:30 INFO mapreduce.Job:  map 32% reduce 0%
17/10/03 10:50:32 INFO mapreduce.Job:  map 33% reduce 0%
17/10/03 10:50:34 INFO mapreduce.Job:  map 34% reduce 0%
17/10/03 10:50:36 INFO mapreduce.Job:  map 35% reduce 0%
17/10/03 10:50:37 INFO mapreduce.Job:  map 36% reduce 0%
17/10/03 10:50:38 INFO mapreduce.Job:  map 37% reduce 0%
17/10/03 10:50:39 INFO mapreduce.Job:  map 39% reduce 0%
17/10/03 10:50:40 INFO mapreduce.Job:  map 42% reduce 0%
17/10/03 10:50:41 INFO mapreduce.Job:  map 43% reduce 0%
17/10/03 10:50:42 INFO mapreduce.Job:  map 44% reduce 0%
17/10/03 10:50:47 INFO mapreduce.Job:  map 45% reduce 0%
17/10/03 10:50:49 INFO mapreduce.Job:  map 46% reduce 0%
17/10/03 10:50:50 INFO mapreduce.Job:  map 47% reduce 0%
17/10/03 10:50:51 INFO mapreduce.Job:  map 49% reduce 0%
17/10/03 10:50:52 INFO mapreduce.Job:  map 52% reduce 0%
17/10/03 10:50:53 INFO mapreduce.Job:  map 54% reduce 0%
17/10/03 10:50:56 INFO mapreduce.Job:  map 55% reduce 0%
17/10/03 10:51:00 INFO mapreduce.Job:  map 56% reduce 0%
17/10/03 10:51:01 INFO mapreduce.Job:  map 58% reduce 0%
17/10/03 10:51:02 INFO mapreduce.Job:  map 60% reduce 0%
17/10/03 10:51:03 INFO mapreduce.Job:  map 63% reduce 0%
17/10/03 10:51:04 INFO mapreduce.Job:  map 64% reduce 0%
17/10/03 10:51:06 INFO mapreduce.Job:  map 65% reduce 0%
17/10/03 10:51:10 INFO mapreduce.Job:  map 66% reduce 0%
17/10/03 10:51:11 INFO mapreduce.Job:  map 67% reduce 0%
17/10/03 10:51:12 INFO mapreduce.Job:  map 69% reduce 0%
17/10/03 10:51:13 INFO mapreduce.Job:  map 71% reduce 0%
17/10/03 10:51:14 INFO mapreduce.Job:  map 72% reduce 0%
17/10/03 10:51:15 INFO mapreduce.Job:  map 73% reduce 0%
17/10/03 10:51:16 INFO mapreduce.Job:  map 75% reduce 0%
17/10/03 10:51:21 INFO mapreduce.Job:  map 77% reduce 0%
17/10/03 10:51:23 INFO mapreduce.Job:  map 78% reduce 0%
17/10/03 10:51:24 INFO mapreduce.Job:  map 80% reduce 0%
17/10/03 10:51:25 INFO mapreduce.Job:  map 81% reduce 0%
17/10/03 10:51:26 INFO mapreduce.Job:  map 82% reduce 0%
17/10/03 10:51:27 INFO mapreduce.Job:  map 83% reduce 0%
17/10/03 10:51:28 INFO mapreduce.Job:  map 85% reduce 0%
17/10/03 10:51:29 INFO mapreduce.Job:  map 86% reduce 0%
17/10/03 10:51:32 INFO mapreduce.Job:  map 88% reduce 0%
17/10/03 10:51:33 INFO mapreduce.Job:  map 89% reduce 0%
17/10/03 10:51:34 INFO mapreduce.Job:  map 90% reduce 0%
17/10/03 10:51:36 INFO mapreduce.Job:  map 91% reduce 0%
17/10/03 10:51:42 INFO mapreduce.Job:  map 92% reduce 0%
17/10/03 10:51:43 INFO mapreduce.Job:  map 94% reduce 0%
17/10/03 10:51:44 INFO mapreduce.Job:  map 95% reduce 2%
17/10/03 10:51:45 INFO mapreduce.Job:  map 96% reduce 10%
17/10/03 10:51:46 INFO mapreduce.Job:  map 96% reduce 12%
17/10/03 10:51:47 INFO mapreduce.Job:  map 96% reduce 20%
17/10/03 10:51:48 INFO mapreduce.Job:  map 96% reduce 28%
17/10/03 10:51:50 INFO mapreduce.Job:  map 97% reduce 30%
17/10/03 10:51:51 INFO mapreduce.Job:  map 99% reduce 30%
17/10/03 10:51:53 INFO mapreduce.Job:  map 100% reduce 30%
17/10/03 10:51:54 INFO mapreduce.Job:  map 100% reduce 32%
17/10/03 10:51:55 INFO mapreduce.Job:  map 100% reduce 37%
17/10/03 10:51:56 INFO mapreduce.Job:  map 100% reduce 38%
17/10/03 10:51:57 INFO mapreduce.Job:  map 100% reduce 40%
17/10/03 10:51:58 INFO mapreduce.Job:  map 100% reduce 47%
17/10/03 10:51:59 INFO mapreduce.Job:  map 100% reduce 51%
17/10/03 10:52:00 INFO mapreduce.Job:  map 100% reduce 59%
17/10/03 10:52:01 INFO mapreduce.Job:  map 100% reduce 66%
17/10/03 10:52:02 INFO mapreduce.Job:  map 100% reduce 67%
17/10/03 10:52:03 INFO mapreduce.Job:  map 100% reduce 73%
17/10/03 10:52:04 INFO mapreduce.Job:  map 100% reduce 76%
17/10/03 10:52:05 INFO mapreduce.Job:  map 100% reduce 78%
17/10/03 10:52:06 INFO mapreduce.Job:  map 100% reduce 79%
17/10/03 10:52:07 INFO mapreduce.Job:  map 100% reduce 82%
17/10/03 10:52:08 INFO mapreduce.Job:  map 100% reduce 83%
17/10/03 10:52:09 INFO mapreduce.Job:  map 100% reduce 84%
17/10/03 10:52:10 INFO mapreduce.Job:  map 100% reduce 85%
17/10/03 10:52:11 INFO mapreduce.Job:  map 100% reduce 86%
17/10/03 10:52:12 INFO mapreduce.Job:  map 100% reduce 87%
17/10/03 10:52:14 INFO mapreduce.Job:  map 100% reduce 88%
17/10/03 10:52:25 INFO mapreduce.Job:  map 100% reduce 91%
17/10/03 10:52:27 INFO mapreduce.Job:  map 100% reduce 93%
17/10/03 10:52:29 INFO mapreduce.Job:  map 100% reduce 94%
17/10/03 10:52:30 INFO mapreduce.Job:  map 100% reduce 97%
17/10/03 10:52:33 INFO mapreduce.Job:  map 100% reduce 98%
17/10/03 10:52:34 INFO mapreduce.Job:  map 100% reduce 99%
17/10/03 10:52:36 INFO mapreduce.Job:  map 100% reduce 100%
17/10/03 10:52:36 INFO mapreduce.Job: Job job_1506998782120_0003 completed successfully
17/10/03 10:52:36 INFO mapreduce.Job: Counters: 50
        File System Counters
                FILE: Number of bytes read=4436101002
                FILE: Number of bytes written=8820016360
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=10000045900
                HDFS: Number of bytes written=10000000000
                HDFS: Number of read operations=948
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=32
        Job Counters
                Launched map tasks=300
                Launched reduce tasks=16
                Data-local map tasks=230
                Rack-local map tasks=70
                Total time spent by all maps in occupied slots (ms)=2956193
                Total time spent by all reduces in occupied slots (ms)=942464
                Total time spent by all map tasks (ms)=2956193
                Total time spent by all reduce tasks (ms)=942464
                Total vcore-milliseconds taken by all map tasks=2956193
                Total vcore-milliseconds taken by all reduce tasks=942464
                Total megabyte-milliseconds taken by all map tasks=3027141632
                Total megabyte-milliseconds taken by all reduce tasks=965083136
        Map-Reduce Framework
                Map input records=100000000
                Map output records=100000000
                Map output bytes=10200000000
                Map output materialized bytes=4342944406
                Input split bytes=45900
                Combine input records=0
                Combine output records=0
                Reduce input groups=100000000
                Reduce shuffle bytes=4342944406
                Reduce input records=100000000
                Reduce output records=100000000
                Spilled Records=200000000
                Shuffled Maps =4800
                Failed Shuffles=0
                Merged Map outputs=4800
                GC time elapsed (ms)=51858
                CPU time spent (ms)=1519010
                Physical memory (bytes) snapshot=171600916480
                Virtual memory (bytes) snapshot=505911693312
                Total committed heap usage (bytes)=189435740160
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=10000000000
        File Output Format Counters
                Bytes Written=10000000000
17/10/03 10:52:36 INFO terasort.TeraSort: done

real    2m56.420s
user    0m7.565s
sys     0m0.335s

--Verificacion archivos

[root@ip-172-31-28-197 ec2-user]# hdfs dfs -ls -h /user/DKvothe/terasort
Found 18 items
-rw-r--r--   1 hdfs supergroup          0 2017-10-03 10:52 /user/DKvothe/terasort/_SUCCESS
-rw-r--r--  10 hdfs supergroup        165 2017-10-03 10:49 /user/DKvothe/terasort/_partition.lst
-rw-r--r--   1 hdfs supergroup    594.1 M 2017-10-03 10:52 /user/DKvothe/terasort/part-r-00000
-rw-r--r--   1 hdfs supergroup    597.6 M 2017-10-03 10:52 /user/DKvothe/terasort/part-r-00001
-rw-r--r--   1 hdfs supergroup    592.1 M 2017-10-03 10:52 /user/DKvothe/terasort/part-r-00002
-rw-r--r--   1 hdfs supergroup    600.6 M 2017-10-03 10:52 /user/DKvothe/terasort/part-r-00003
-rw-r--r--   1 hdfs supergroup    590.6 M 2017-10-03 10:52 /user/DKvothe/terasort/part-r-00004
-rw-r--r--   1 hdfs supergroup    602.3 M 2017-10-03 10:52 /user/DKvothe/terasort/part-r-00005
-rw-r--r--   1 hdfs supergroup    586.5 M 2017-10-03 10:52 /user/DKvothe/terasort/part-r-00006
-rw-r--r--   1 hdfs supergroup    586.2 M 2017-10-03 10:52 /user/DKvothe/terasort/part-r-00007
-rw-r--r--   1 hdfs supergroup    599.5 M 2017-10-03 10:52 /user/DKvothe/terasort/part-r-00008
-rw-r--r--   1 hdfs supergroup    593.9 M 2017-10-03 10:52 /user/DKvothe/terasort/part-r-00009
-rw-r--r--   1 hdfs supergroup    610.3 M 2017-10-03 10:52 /user/DKvothe/terasort/part-r-00010
-rw-r--r--   1 hdfs supergroup    585.9 M 2017-10-03 10:52 /user/DKvothe/terasort/part-r-00011
-rw-r--r--   1 hdfs supergroup    602.4 M 2017-10-03 10:52 /user/DKvothe/terasort/part-r-00012
-rw-r--r--   1 hdfs supergroup    600.8 M 2017-10-03 10:52 /user/DKvothe/terasort/part-r-00013
-rw-r--r--   1 hdfs supergroup    612.7 M 2017-10-03 10:52 /user/DKvothe/terasort/part-r-00014
-rw-r--r--   1 hdfs supergroup    581.2 M 2017-10-03 10:52 /user/DKvothe/terasort/part-r-00015

