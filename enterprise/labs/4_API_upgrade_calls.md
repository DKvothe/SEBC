##Revisar version de api

curl -u dkvothe:cloudera 'http://ec2-18-221-155-15.us-east-2.compute.amazonaws.com:7180/api/version'
v17

##Version CM


[root@ip-172-31-26-69 ec2-user]# curl -u dkvothe:cloudera 'http://ec2-18-221-155-15.us-east-2.compute.amazonaws.com:7180/api/v17/cm/version'
{
  "version" : "5.12.1",
  "buildUser" : "jenkins",
  "buildTimestamp" : "20170818-0807",
  "gitHash" : "9bdee611802535491d400e03c98ef694a2c77d0a",
  "snapshot" : false
}

##Usuarios en CM

[root@ip-172-31-26-69 ec2-user]# curl -u dkvothe:cloudera 'http://ec2-18-221-155-15.us-east-2.compute.amazonaws.com:7180/api/v17/uers'
{
  "items" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ]
  }, {
    "name" : "dkvothe",
    "roles" : [ "ROLE_ADMIN" ]
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ]
  } ]
}[


##Server utilizado

[root@ip-172-31-26-69 ec2-user]# curl -u dkvothe:cloudera 'http://ec2-18-221-155-15.us-east-2.compute.amazonaws.com:7180/api/v17/cm/scmDbInfo'
{
  "scmDbType" : "MYSQL",
  "embeddedDbUsed" : false
}[
