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
--creacion de usuarios

--tablas con george

Beeline version 1.1.0-cdh5.11.2 by Apache Hive
beeline> !connect jdbc:hive2://ip-172-31-26-220.us-east-2.compute.internal:10000/default;principal=hive/_HOST@DKVOTHE.COM
scan complete in 2ms
Connecting to jdbc:hive2://ip-172-31-26-220.us-east-2.compute.internal:10000/default;principal=hive/_HOST@DKVOTHE.COM
Connected to: Apache Hive (version 1.1.0-cdh5.11.2)
Driver: Hive JDBC (version 1.1.0-cdh5.11.2)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-26-220.us-east-2.co> show tables;
INFO  : Compiling command(queryId=hive_20171004185555_ae5f8dd6-6e1f-4882-b056-db12883463f6): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171004185555_ae5f8dd6-6e1f-4882-b056-db12883463f6); Time taken: 0.064 seconds
INFO  : Executing command(queryId=hive_20171004185555_ae5f8dd6-6e1f-4882-b056-db12883463f6): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171004185555_ae5f8dd6-6e1f-4882-b056-db12883463f6); Time taken: 0.134 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.288 seconds)
0: jdbc:hive2://ip-172-31-26-220.us-east-2.co>


--tablas con ferdinand


[root@ip-172-31-26-27 ec2-user]# beeline
Beeline version 1.1.0-cdh5.11.2 by Apache Hive
beeline> !connect jdbc:hive2://ip-172-31-26-220.us-east-2.compute.internal:10000/default;principal=hive/_HOST@DKVOTHE.COM
scan complete in 2ms
Connecting to jdbc:hive2://ip-172-31-26-220.us-east-2.compute.internal:10000/default;principal=hive/_HOST@DKVOTHE.COM
Connected to: Apache Hive (version 1.1.0-cdh5.11.2)
Driver: Hive JDBC (version 1.1.0-cdh5.11.2)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-26-220.us-east-2.co> show tables;
INFO  : Compiling command(queryId=hive_20171004185858_c9ad3491-5137-4c90-9797-04ffaef41a66): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171004185858_c9ad3491-5137-4c90-9797-04ffaef41a66); Time taken: 0.067 seconds
INFO  : Executing command(queryId=hive_20171004185858_c9ad3491-5137-4c90-9797-04ffaef41a66): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171004185858_c9ad3491-5137-4c90-9797-04ffaef41a66); Time taken: 0.127 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.284 seconds)
0: jdbc:hive2://ip-172-31-26-220.us-east-2.co>
