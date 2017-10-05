##Detener hive

[ec2-user@ip-172-31-26-69 ~]$ curl -X POST -u DKvothe:cloudera 'http://localhost:7180/api/v16/clusters/DKvothe/services/hive/commads/stop'
{
  "id" : 1901,
  "name" : "Stop",
  "startTime" : "2017-10-05T14:44:48.476Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }

##Iniciar Hive

[ec2-user@ip-172-31-26-69 ~]$ curl -X POST -u DKvothe:cloudera 'http://localhost:7180/api/v16/clusters/DKvothe/services/hive/commads/start'
{
  "id" : 1907,
  "name" : "Start",
  "startTime" : "2017-10-05T14:45:42.810Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}

## Revisar esstado de Hive

curl -u DKvothe:cloudera \
  'http://localhost:7180/api/v1/clusters/DKvothe/services/hive/config'
  
## Salida de comando

[ec2-user@ip-172-31-26-69 ~]$ curl -u DKvothe:cloudera \
>   'http://localhost:7180/api/v1/clusters/DKvothe/services/hive/config'
{
  "roleTypeConfigs" : [ {
    "roleType" : "HIVEMETASTORE",
    "items" : [ {
      "name" : "hive_metastore_server_max_message_size",
      "value" : "858993459"
    } ]
  }, {
    "roleType" : "HIVESERVER2",
    "items" : [ {
      "name" : "hiveserver2_enable_impersonation",
      "value" : "false"
    }, {
      "name" : "hiveserver2_spark_driver_memory",
      "value" : "966367641"
    }, {
      "name" : "hiveserver2_spark_executor_cores",
      "value" : "6"
    }, {
      "name" : "hiveserver2_spark_executor_memory",
      "value" : "10390654156"
    }, {
      "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
      "value" : "102"
    }, {
      "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
      "value" : "1748"
    } ]
  } ],
  "items" : [ {
    "name" : "hive_metastore_database_host",
    "value" : "ip-172-31-26-69.us-east-2.compute.internal"
  }, {
    "name" : "hive_metastore_database_password",
    "value" : "hive_password"
  }, {
    "name" : "hive_proxy_user_groups_list",
    "value" : "hive,hue"
  }, {
    "name" : "mapreduce_yarn_service",
    "value" : "yarn"
  }, {
    "name" : "sentry_service",
    "value" : "sentry"
  }, {
    "name" : "zookeeper_service",
    "value" : "zookeeper"
  } ]
