```

``[root@ip-172-31-28-197 ec2-user]# kinit dkvothe
Password for dkvothe@DKVOTHE.COM:
[root@ip-172-31-28-197 ec2-user]# beeline
Beeline version 1.1.0-cdh5.11.2 by Apache Hive
beeline> !connect jdbc:hive2://ip-172-31-26-220.us-east-2.compute.internal:10000/default;principal=hive/_HOST@DKVOTHE.COM
scan complete in 2ms
Connecting to jdbc:hive2://ip-172-31-26-220.us-east-2.compute.internal:10000/default;principal=hive/_HOST@DKVOTHE.COM
Connected to: Apache Hive (version 1.1.0-cdh5.11.2)
Driver: Hive JDBC (version 1.1.0-cdh5.11.2)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-26-220.us-east-2.co> show tables;
INFO  : Compiling command(queryId=hive_20171004184747_2855ade5-be8a-4950-9237-b0ef684d04da): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171004184747_2855ade5-be8a-4950-9237-b0ef684d04da); Time taken: 0.602 seconds
INFO  : Executing command(queryId=hive_20171004184747_2855ade5-be8a-4950-9237-b0ef684d04da): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171004184747_2855ade5-be8a-4950-9237-b0ef684d04da); Time taken: 0.239 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (2.166 seconds)
0: jdbc:hive2://ip-172-31-26-220.us-east-2.co>
`
