## directorios de usuarios

[root@ip-172-31-36-67 ec2-user]# hdfs dfs -ls /user
Found 4 items
drwxr-xr-x   - haley  supergroup          0 2017-10-06 11:19 /user/haley
drwxrwxrwx   - mapred hadoop              0 2017-10-06 11:09 /user/history
drwxr-xr-x   - saturn supergroup          0 2017-10-06 11:18 /user/saturn
drwxr-x--x   - spark  spark               0 2017-10-06 11:14 /user/spark

##Hosts

[root@ip-172-31-43-186 ec2-user]# curl -u admin:admin 'http://ec2-13-59-234-206.us-east-2.compute.amazonaws.com:7180/api/v14/hosts'
{
  "items" : [ {
    "hostId" : "e9169297-0b11-4ea8-a377-30ed2b72625a",
    "ipAddress" : "172.31.35.152",
    "hostname" : "ip-172-31-35-152.us-east-2.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-42-135.us-east-2.compute.internal:7180/cmf/hostRedirect/e9169297-0b11-4ea8-a377-30ed2b72625a",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 33299820544
  }, {
    "hostId" : "c7c408b9-5ba4-41da-885e-189c091a0d0c",
    "ipAddress" : "172.31.36.67",
    "hostname" : "ip-172-31-36-67.us-east-2.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-42-135.us-east-2.compute.internal:7180/cmf/hostRedirect/c7c408b9-5ba4-41da-885e-189c091a0d0c",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 33299820544
  }, {
    "hostId" : "3bf9f4ed-6678-4b8a-839d-e7b14a9dc2ef",
    "ipAddress" : "172.31.42.135",
    "hostname" : "ip-172-31-42-135.us-east-2.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-42-135.us-east-2.compute.internal:7180/cmf/hostRedirect/3bf9f4ed-6678-4b8a-839d-e7b14a9dc2ef",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 33299820544
  }, {
    "hostId" : "061ff784-3b8b-41cc-8549-72f49d16d54d",
    "ipAddress" : "172.31.43.186",
    "hostname" : "ip-172-31-43-186.us-east-2.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-42-135.us-east-2.compute.internal:7180/cmf/hostRedirect/061ff784-3b8b-41cc-8549-72f49d16d54d",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 33299820544
  } ]
}

##service

[root@ip-172-31-43-186 ec2-user]# curl -u admin:admin 'http://ec2-13-59-234-206.us-east-2.compute.amazonaws.com:7180/api/v8/clusters/dkvothe/services'
{
  "items" : [ {
    "name" : "hdfs",
    "type" : "HDFS",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-42-135.us-east-2.compute.internal:7180/cmf/serviceRedirect/hdfs",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "HDFS_BLOCKS_WITH_CORRUPT_REPLICAS",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_CANARY_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_DATA_NODES_HEALTHY",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_FREE_SPACE_REMAINING",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_HA_NAMENODE_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_MISSING_BLOCKS",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_UNDER_REPLICATED_BLOCKS",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "HDFS"
  }, {
    "name" : "yarn",
    "type" : "YARN",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-42-135.us-east-2.compute.internal:7180/cmf/serviceRedirect/yarn",
    "serviceState" : "STARTED",
    "healthSummary" : "BAD",
    "healthChecks" : [ {
      "name" : "YARN_JOBHISTORY_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "YARN_NODE_MANAGERS_HEALTHY",
      "summary" : "BAD"
    }, {
      "name" : "YARN_RESOURCEMANAGERS_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "YARN_USAGE_AGGREGATION_HEALTH",
      "summary" : "DISABLED"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "YARN (MR2 Included)"
  }, {
    "name" : "spark_on_yarn",
    "type" : "SPARK_ON_YARN",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-42-135.us-east-2.compute.internal:7180/cmf/serviceRedirect/spark_on_yarn",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Spark"
  } ]
}[
