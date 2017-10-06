##Comando teragen

time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapred.map.tasks=12 -Dmapreduce.map.memory.mb=512 -Ddfs.block.size=33554432 65536000  /user/saturn/teragen

##Resultado

7/10/06 11:56:27 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-36-67.us-east-2.compute.internal/172.31.36.67:8032
17/10/06 11:56:28 INFO terasort.TeraSort: Generating 65536000 using 12
17/10/06 11:56:28 INFO mapreduce.JobSubmitter: number of splits:12
17/10/06 11:56:28 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/10/06 11:56:28 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
17/10/06 11:56:28 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1507303708705_0001
17/10/06 11:56:29 INFO impl.YarnClientImpl: Submitted application application_1507303708705_0001
17/10/06 11:56:29 INFO mapreduce.Job: The url to track the job: http://ip-172-31-36-67.us-east-2.compute.internal:8088/proxy/application_1507303708705_0001/
17/10/06 11:56:29 INFO mapreduce.Job: Running job: job_1507303708705_0001
17/10/06 11:56:34 INFO mapreduce.Job: Job job_1507303708705_0001 running in uber mode : false
17/10/06 11:56:34 INFO mapreduce.Job:  map 0% reduce 0%
17/10/06 11:56:47 INFO mapreduce.Job:  map 4% reduce 0%
17/10/06 11:56:48 INFO mapreduce.Job:  map 8% reduce 0%
17/10/06 11:56:50 INFO mapreduce.Job:  map 13% reduce 0%
17/10/06 11:56:51 INFO mapreduce.Job:  map 16% reduce 0%
17/10/06 11:56:53 INFO mapreduce.Job:  map 20% reduce 0%
17/10/06 11:56:54 INFO mapreduce.Job:  map 22% reduce 0%
17/10/06 11:56:56 INFO mapreduce.Job:  map 25% reduce 0%
17/10/06 11:56:57 INFO mapreduce.Job:  map 27% reduce 0%
17/10/06 11:56:59 INFO mapreduce.Job:  map 31% reduce 0%
17/10/06 11:57:00 INFO mapreduce.Job:  map 33% reduce 0%
17/10/06 11:57:02 INFO mapreduce.Job:  map 36% reduce 0%
17/10/06 11:57:03 INFO mapreduce.Job:  map 39% reduce 0%
17/10/06 11:57:05 INFO mapreduce.Job:  map 42% reduce 0%
17/10/06 11:57:06 INFO mapreduce.Job:  map 44% reduce 0%
17/10/06 11:57:08 INFO mapreduce.Job:  map 47% reduce 0%
17/10/06 11:57:09 INFO mapreduce.Job:  map 50% reduce 0%
17/10/06 11:57:10 INFO mapreduce.Job:  map 51% reduce 0%
17/10/06 11:57:11 INFO mapreduce.Job:  map 53% reduce 0%
17/10/06 11:57:12 INFO mapreduce.Job:  map 56% reduce 0%
17/10/06 11:57:13 INFO mapreduce.Job:  map 57% reduce 0%
17/10/06 11:57:14 INFO mapreduce.Job:  map 58% reduce 0%
17/10/06 11:57:20 INFO mapreduce.Job:  map 66% reduce 0%
17/10/06 11:57:22 INFO mapreduce.Job:  map 69% reduce 0%
17/10/06 11:57:23 INFO mapreduce.Job:  map 71% reduce 0%
17/10/06 11:57:24 INFO mapreduce.Job:  map 75% reduce 0%
17/10/06 11:57:25 INFO mapreduce.Job:  map 76% reduce 0%
17/10/06 11:57:26 INFO mapreduce.Job:  map 79% reduce 0%
17/10/06 11:57:27 INFO mapreduce.Job:  map 81% reduce 0%
17/10/06 11:57:28 INFO mapreduce.Job:  map 82% reduce 0%
17/10/06 11:57:29 INFO mapreduce.Job:  map 83% reduce 0%
17/10/06 11:57:30 INFO mapreduce.Job:  map 86% reduce 0%
17/10/06 11:57:31 INFO mapreduce.Job:  map 87% reduce 0%
17/10/06 11:57:32 INFO mapreduce.Job:  map 90% reduce 0%
17/10/06 11:57:33 INFO mapreduce.Job:  map 92% reduce 0%
17/10/06 11:57:34 INFO mapreduce.Job:  map 94% reduce 0%
17/10/06 11:57:36 INFO mapreduce.Job:  map 99% reduce 0%
17/10/06 11:57:37 INFO mapreduce.Job:  map 100% reduce 0%
17/10/06 11:57:37 INFO mapreduce.Job: Job job_1507303708705_0001 completed successfully
17/10/06 11:57:38 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=1483886
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=1025
                HDFS: Number of bytes written=6553600000
                HDFS: Number of read operations=48
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=24
        Job Counters
                Launched map tasks=12
                Other local map tasks=12
                Total time spent by all maps in occupied slots (ms)=360484
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=360484
                Total vcore-seconds taken by all map tasks=360484
                Total megabyte-seconds taken by all map tasks=369135616
        Map-Reduce Framework
                Map input records=65536000
                Map output records=65536000
                Input split bytes=1025
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=3166
                CPU time spent (ms)=140010
                Physical memory (bytes) snapshot=2530144256
                Virtual memory (bytes) snapshot=13775085568
                Total committed heap usage (bytes)=4632608768
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=140750829423462787
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=6553600000
##Time

real    1m12.297s
user    0m4.556s
sys     0m0.258s


## Comando ls

[root@ip-172-31-43-186 ec2-user]# hdfs dfs -ls /user/saturn/teragen
Found 13 items
-rw-r--r--   3 saturn supergroup          0 2017-10-06 11:57 /user/saturn/teragen/_SUCCESS
-rw-r--r--   3 saturn supergroup  546133400 2017-10-06 11:57 /user/saturn/teragen/part-m-00000
-rw-r--r--   3 saturn supergroup  546133300 2017-10-06 11:57 /user/saturn/teragen/part-m-00001
-rw-r--r--   3 saturn supergroup  546133300 2017-10-06 11:57 /user/saturn/teragen/part-m-00002
-rw-r--r--   3 saturn supergroup  546133400 2017-10-06 11:57 /user/saturn/teragen/part-m-00003
-rw-r--r--   3 saturn supergroup  546133300 2017-10-06 11:57 /user/saturn/teragen/part-m-00004
-rw-r--r--   3 saturn supergroup  546133300 2017-10-06 11:57 /user/saturn/teragen/part-m-00005
-rw-r--r--   3 saturn supergroup  546133400 2017-10-06 11:57 /user/saturn/teragen/part-m-00006
-rw-r--r--   3 saturn supergroup  546133300 2017-10-06 11:57 /user/saturn/teragen/part-m-00007
-rw-r--r--   3 saturn supergroup  546133300 2017-10-06 11:57 /user/saturn/teragen/part-m-00008
-rw-r--r--   3 saturn supergroup  546133400 2017-10-06 11:57 /user/saturn/teragen/part-m-00009
-rw-r--r--   3 saturn supergroup  546133300 2017-10-06 11:57 /user/saturn/teragen/part-m-00010
-rw-r--r--   3 saturn supergroup  546133300 2017-10-06 11:57 /user/saturn/teragen/part-m-00011


##Bloques Saturn

[root@ip-172-31-43-186 ec2-user]# hadoop fsck -blocks /user/saturn
DEPRECATED: Use of this script to execute hdfs command is deprecated.
Instead use the hdfs command for it.

Connecting to namenode via http://ip-172-31-35-152.us-east-2.compute.internal:50070
FSCK started by saturn (auth:SIMPLE) from /172.31.43.186 for path /user/saturn at Fri Oct 06 12:01:05 EDT 2017
.............Status: HEALTHY
 Total size:    6553600000 B
 Total dirs:    3
 Total files:   13
 Total symlinks:                0
 Total blocks (validated):      204 (avg. block size 32125490 B)
 Minimally replicated blocks:   204 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          3
 Number of racks:               1
FSCK ended at Fri Oct 06 12:01:05 EDT 2017 in 10 milliseconds


The filesystem under path '/user/saturn' is HEALTHY



