{
  "timestamp" : "2017-10-05T14:28:46.878Z",
  "clusters" : [ {
    "name" : "cluster",
    "displayName" : "DKvothe",
    "version" : "CDH5",
    "fullVersion" : "5.11.2",
    "services" : [ {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "items" : [ {
          "name" : "hadoop_secure_web_ui",
          "value" : "true",
          "sensitive" : false
        }, {
          "name" : "hdfs_service",
          "value" : "hdfs",
          "sensitive" : false
        }, {
          "name" : "rm_dirty",
          "value" : "false",
          "sensitive" : false
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "80",
          "sensitive" : false
        }, {
          "name" : "yarn_service_cgroups",
          "value" : "false",
          "sensitive" : false
        }, {
          "name" : "yarn_service_lce_always",
          "value" : "false",
          "sensitive" : false
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "eW9QNDzqR6nUoGagZ106msh82omLBy",
          "sensitive" : true
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-b405929b0cf89b7528ef3250eb78693b",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "372e1e1a-7511-48e8-89e1-7ff1c71df81b"
        },
        "config" : {
          "items" : [ {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":10737418240,\"critical\":3221225472}",
            "sensitive" : false
          }, {
            "name" : "role_jceks_password",
            "value" : "c7z6j621md0ecaplbgybafvbm",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-JOBHISTORY-BASE"
        }
      }, {
        "name" : "yarn-NODEMANAGER-249c706dfbdf343dfea28b0188d112c9",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "3192d069-25c9-4a6d-b3c8-77ee1d380856"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "13rklvi16z22jnwd9d7t94iws",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-NODEMANAGER-1"
        }
      }, {
        "name" : "yarn-NODEMANAGER-8c7c310713f5bea96630dcbe92535bb2",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "5a75aa6c-6e01-454a-81a0-943ad8619b5d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9h5pkg0tjahi585dyusdc0mo8",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-NODEMANAGER-BASE"
        }
      }, {
        "name" : "yarn-NODEMANAGER-eff6992d50eb43f0a40d7a213270f7c3",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "78f0a267-18ca-4aeb-93e9-a61ea942350c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5ay73x2weioyr1lk0i0obxs7l",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-NODEMANAGER-2"
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-8c7c310713f5bea96630dcbe92535bb2",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "5a75aa6c-6e01-454a-81a0-943ad8619b5d"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "29",
            "sensitive" : false
          }, {
            "name" : "role_jceks_password",
            "value" : "118q1bv5ym31xbxps2bc24jty",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-RESOURCEMANAGER-BASE"
        }
      } ],
      "displayName" : "YARN (MR2 Included)",
      "roleConfigGroups" : [ {
        "name" : "yarn-GATEWAY-BASE",
        "displayName" : "Gateway Default Group",
        "roleType" : "GATEWAY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "16",
            "sensitive" : false
          }, {
            "name" : "mapred_submit_replication",
            "value" : "2",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "yarn-JOBHISTORY-BASE",
        "displayName" : "JobHistory Server Default Group",
        "roleType" : "JOBHISTORY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-1",
        "displayName" : "NodeManager Group 1",
        "roleType" : "NODEMANAGER",
        "base" : false,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":10737418240,\"critical\":3758096384}",
            "sensitive" : false
          }, {
            "name" : "nodemanager_recovery_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":10737418240,\"critical\":3221225472}",
            "sensitive" : false
          }, {
            "name" : "rm_cpu_shares",
            "value" : "1600",
            "sensitive" : false
          }, {
            "name" : "rm_io_weight",
            "value" : "800",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/disco1/yarn/nm,/disco2/yarn/nm",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/disco1/yarn/container-logs,/disco2/yarn/container-logs",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "6",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "17916",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-2",
        "displayName" : "NodeManager Group 2",
        "roleType" : "NODEMANAGER",
        "base" : false,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":10737418240,\"critical\":2684354560}",
            "sensitive" : false
          }, {
            "name" : "nodemanager_recovery_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":10737418240,\"critical\":2684354560}",
            "sensitive" : false
          }, {
            "name" : "rm_cpu_shares",
            "value" : "1600",
            "sensitive" : false
          }, {
            "name" : "rm_io_weight",
            "value" : "800",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/disco1/yarn/nm,/disco2/yarn/nm",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/disco1/yarn/container-logs,/disco2/yarn/container-logs",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "6",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "11658",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-3",
        "displayName" : "NodeManager Group 3",
        "roleType" : "NODEMANAGER",
        "base" : false,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2684354560,\"critical\":1572864000}",
            "sensitive" : false
          }, {
            "name" : "nodemanager_recovery_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2684354560,\"critical\":1572864000}",
            "sensitive" : false
          }, {
            "name" : "rm_cpu_shares",
            "value" : "2000",
            "sensitive" : false
          }, {
            "name" : "rm_io_weight",
            "value" : "1000",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/disco1/yarn/nm,/disco2/yarn/nm",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/disco1/yarn/container-logs,/disco2/yarn/container-logs",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "8",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "14013",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-BASE",
        "displayName" : "NodeManager Default Group",
        "roleType" : "NODEMANAGER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":10737418240,\"critical\":2684354560}",
            "sensitive" : false
          }, {
            "name" : "nodemanager_recovery_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":10737418240,\"critical\":2684354560}",
            "sensitive" : false
          }, {
            "name" : "rm_cpu_shares",
            "value" : "1600",
            "sensitive" : false
          }, {
            "name" : "rm_io_weight",
            "value" : "800",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/disco1/yarn/nm,/disco2/yarn/nm",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/disco1/yarn/container-logs,/disco2/yarn/container-logs",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "6",
            "sensitive" : false
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "16650",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-BASE",
        "displayName" : "ResourceManager Default Group",
        "roleType" : "RESOURCEMANAGER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":10737418240,\"critical\":2684354560}",
            "sensitive" : false
          }, {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "17916",
            "sensitive" : false
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "8",
            "sensitive" : false
          } ]
        }
      } ]
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "items" : [ {
          "name" : "dfs_encrypt_data_transfer_algorithm",
          "value" : "AES/CTR/NoPadding",
          "sensitive" : false
        }, {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "T41C5DAyJmVh5zNoMHQ8mbRCJXIwKb",
          "sensitive" : true
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "9wASdCfQ3UVk36eZIC1Hpei31XoYJV",
          "sensitive" : true
        }, {
          "name" : "hadoop_secure_web_ui",
          "value" : "true",
          "sensitive" : false
        }, {
          "name" : "hadoop_security_authentication",
          "value" : "kerberos",
          "sensitive" : false
        }, {
          "name" : "hadoop_security_authorization",
          "value" : "true",
          "sensitive" : false
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "oMUwSy2s15MTOdkPe5Ptz793CpaLoD",
          "sensitive" : true
        }, {
          "name" : "rm_dirty",
          "value" : "false",
          "sensitive" : false
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "20",
          "sensitive" : false
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper",
          "sensitive" : false
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-eff6992d50eb43f0a40d7a213270f7c3",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "78f0a267-18ca-4aeb-93e9-a61ea942350c"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-BALANCER-BASE"
        }
      }, {
        "name" : "hdfs-DATANODE-249c706dfbdf343dfea28b0188d112c9",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "3192d069-25c9-4a6d-b3c8-77ee1d380856"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6vftzvxm1q6o8xbcxfsqo6gbe",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-DATANODE-BASE"
        }
      }, {
        "name" : "hdfs-DATANODE-8c7c310713f5bea96630dcbe92535bb2",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "5a75aa6c-6e01-454a-81a0-943ad8619b5d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "p1hqce5u7grputlk4tesw0qb",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-DATANODE-BASE"
        }
      }, {
        "name" : "hdfs-DATANODE-eff6992d50eb43f0a40d7a213270f7c3",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "78f0a267-18ca-4aeb-93e9-a61ea942350c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2p0vxcmykq2k1fjbo5rcna08m",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-DATANODE-BASE"
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-b405929b0cf89b7528ef3250eb78693b",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "372e1e1a-7511-48e8-89e1-7ff1c71df81b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "86zah2bui5zpsd9zmkrsyolmg",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-FAILOVERCONTROLLER-BASE"
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-eff6992d50eb43f0a40d7a213270f7c3",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "78f0a267-18ca-4aeb-93e9-a61ea942350c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "aqvr29va712sx6q0rhylioqjt",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-FAILOVERCONTROLLER-BASE"
        }
      }, {
        "name" : "hdfs-HTTPFS-8c7c310713f5bea96630dcbe92535bb2",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "5a75aa6c-6e01-454a-81a0-943ad8619b5d"
        },
        "config" : {
          "items" : [ {
            "name" : "oom_heap_dump_dir",
            "value" : "/disco2/tmp",
            "sensitive" : false
          }, {
            "name" : "role_jceks_password",
            "value" : "dpdgo72tvvu56saxxevczanhw",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-HTTPFS-BASE"
        }
      }, {
        "name" : "hdfs-JOURNALNODE-249c706dfbdf343dfea28b0188d112c9",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "3192d069-25c9-4a6d-b3c8-77ee1d380856"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7mgrduwu9ssaaip3hvxr9mxqh",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-JOURNALNODE-BASE"
        }
      }, {
        "name" : "hdfs-JOURNALNODE-8c7c310713f5bea96630dcbe92535bb2",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "5a75aa6c-6e01-454a-81a0-943ad8619b5d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4b91nfobne92la2dv2q3d6w1t",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-JOURNALNODE-BASE"
        }
      }, {
        "name" : "hdfs-JOURNALNODE-b405929b0cf89b7528ef3250eb78693b",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "372e1e1a-7511-48e8-89e1-7ff1c71df81b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9uae41bxv73bort4w87m1kqq9",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-JOURNALNODE-BASE"
        }
      }, {
        "name" : "hdfs-NAMENODE-b405929b0cf89b7528ef3250eb78693b",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "372e1e1a-7511-48e8-89e1-7ff1c71df81b"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true",
            "sensitive" : false
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1",
            "sensitive" : false
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1",
            "sensitive" : false
          }, {
            "name" : "namenode_id",
            "value" : "43",
            "sensitive" : false
          }, {
            "name" : "role_jceks_password",
            "value" : "1y8lgf2t56zisskgiaowlupbk",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-NAMENODE-BASE"
        }
      }, {
        "name" : "hdfs-NAMENODE-eff6992d50eb43f0a40d7a213270f7c3",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "78f0a267-18ca-4aeb-93e9-a61ea942350c"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true",
            "sensitive" : false
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1",
            "sensitive" : false
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1",
            "sensitive" : false
          }, {
            "name" : "namenode_id",
            "value" : "31",
            "sensitive" : false
          }, {
            "name" : "role_jceks_password",
            "value" : "8tot8dfosdx2qlrer2cur5wek",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-NAMENODE-BASE"
        }
      } ],
      "displayName" : "HDFS",
      "roleConfigGroups" : [ {
        "name" : "hdfs-BALANCER-BASE",
        "displayName" : "Balancer Default Group",
        "roleType" : "BALANCER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-BASE",
        "displayName" : "DataNode Default Group",
        "roleType" : "DATANODE",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "datanode_java_heapsize",
            "value" : "1073741824",
            "sensitive" : false
          }, {
            "name" : "dfs_data_dir_list",
            "value" : "/disco1/dfs/dn,/disco2/dfs/dn",
            "sensitive" : false
          }, {
            "name" : "dfs_datanode_data_dir_perm",
            "value" : "700",
            "sensitive" : false
          }, {
            "name" : "dfs_datanode_failed_volumes_tolerated",
            "value" : "1",
            "sensitive" : false
          }, {
            "name" : "dfs_datanode_http_port",
            "value" : "1006",
            "sensitive" : false
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4294967296",
            "sensitive" : false
          }, {
            "name" : "dfs_datanode_port",
            "value" : "1004",
            "sensitive" : false
          }, {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2684354560,\"critical\":1572864000}",
            "sensitive" : false
          }, {
            "name" : "rm_cpu_shares",
            "value" : "400",
            "sensitive" : false
          }, {
            "name" : "rm_io_weight",
            "value" : "200",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-BASE",
        "displayName" : "Failover Controller Default Group",
        "roleType" : "FAILOVERCONTROLLER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2684354560,\"critical\":1610612736}",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "hdfs-GATEWAY-BASE",
        "displayName" : "Gateway Default Group",
        "roleType" : "GATEWAY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "dfs_client_use_trash",
            "value" : "true",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "hdfs-HTTPFS-BASE",
        "displayName" : "HttpFS Default Group",
        "roleType" : "HTTPFS",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-BASE",
        "displayName" : "JournalNode Default Group",
        "roleType" : "JOURNALNODE",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "dfs_journalnode_edits_dir",
            "value" : "/disco2/jn",
            "sensitive" : false
          }, {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":2684354560,\"critical\":1610612736}",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-BASE",
        "displayName" : "NameNode Default Group",
        "roleType" : "NAMENODE",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/disco1/dfs/nn,/disco2/dfs/nn",
            "sensitive" : false
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022",
            "sensitive" : false
          }, {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":3221225472,\"critical\":1073741824}",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "hdfs-NFSGATEWAY-BASE",
        "displayName" : "NFS Gateway Default Group",
        "roleType" : "NFSGATEWAY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-SECONDARYNAMENODE-BASE",
        "displayName" : "SecondaryNameNode Default Group",
        "roleType" : "SECONDARYNAMENODE",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/disco1/dfs/snn",
            "sensitive" : false
          }, {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":10737418240,\"critical\":3221225472}",
            "sensitive" : false
          } ]
        }
      } ],
      "replicationSchedules" : [ ],
      "snapshotPolicies" : [ ]
    }, {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "items" : [ {
          "name" : "enableSecurity",
          "value" : "true",
          "sensitive" : false
        } ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-249c706dfbdf343dfea28b0188d112c9",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "3192d069-25c9-4a6d-b3c8-77ee1d380856"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4wtl2iig2go8zw43wp46b3db5",
            "sensitive" : true
          }, {
            "name" : "serverId",
            "value" : "1",
            "sensitive" : false
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "zookeeper-SERVER-BASE"
        }
      }, {
        "name" : "zookeeper-SERVER-b405929b0cf89b7528ef3250eb78693b",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "372e1e1a-7511-48e8-89e1-7ff1c71df81b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3movf3pah7uscbq0629ghv31h",
            "sensitive" : true
          }, {
            "name" : "serverId",
            "value" : "3",
            "sensitive" : false
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "zookeeper-SERVER-BASE"
        }
      }, {
        "name" : "zookeeper-SERVER-eff6992d50eb43f0a40d7a213270f7c3",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "78f0a267-18ca-4aeb-93e9-a61ea942350c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "c5pme1me9h9ot2lnviv1jv691",
            "sensitive" : true
          }, {
            "name" : "serverId",
            "value" : "2",
            "sensitive" : false
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "zookeeper-SERVER-BASE"
        }
      } ],
      "displayName" : "ZooKeeper",
      "roleConfigGroups" : [ {
        "name" : "zookeeper-SERVER-BASE",
        "displayName" : "Server Default Group",
        "roleType" : "SERVER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "zookeeper"
        },
        "config" : {
          "items" : [ {
            "name" : "dataDir",
            "value" : "/var/log/zookeeper",
            "sensitive" : false
          }, {
            "name" : "dataLogDir",
            "value" : "/var/log/zookeeper",
            "sensitive" : false
          }, {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":10737418240,\"critical\":2684354560}",
            "sensitive" : false
          }, {
            "name" : "zookeeper_server_java_heapsize",
            "value" : "52428800",
            "sensitive" : false
          } ]
        }
      } ]
    }, {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "ip-172-31-26-69.us-east-2.compute.internal",
          "sensitive" : false
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "hive_password",
          "sensitive" : true
        }, {
          "name" : "hive_proxy_user_groups_list",
          "value" : "hive,hue",
          "sensitive" : false
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn",
          "sensitive" : false
        }, {
          "name" : "sentry_service",
          "value" : "sentry",
          "sensitive" : false
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper",
          "sensitive" : false
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-249c706dfbdf343dfea28b0188d112c9",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "3192d069-25c9-4a6d-b3c8-77ee1d380856"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
        }
      }, {
        "name" : "hive-GATEWAY-8c7c310713f5bea96630dcbe92535bb2",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "5a75aa6c-6e01-454a-81a0-943ad8619b5d"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
        }
      }, {
        "name" : "hive-GATEWAY-b405929b0cf89b7528ef3250eb78693b",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "372e1e1a-7511-48e8-89e1-7ff1c71df81b"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
        }
      }, {
        "name" : "hive-GATEWAY-eff6992d50eb43f0a40d7a213270f7c3",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "78f0a267-18ca-4aeb-93e9-a61ea942350c"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
        }
      }, {
        "name" : "hive-HIVEMETASTORE-b405929b0cf89b7528ef3250eb78693b",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "372e1e1a-7511-48e8-89e1-7ff1c71df81b"
        },
        "config" : {
          "items" : [ {
            "name" : "oom_heap_dump_dir",
            "value" : "/disco2/tmp",
            "sensitive" : false
          }, {
            "name" : "role_jceks_password",
            "value" : "3jmk820iwsoxsikff6sc7dvnj",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-HIVEMETASTORE-BASE"
        }
      }, {
        "name" : "hive-HIVESERVER2-b405929b0cf89b7528ef3250eb78693b",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "372e1e1a-7511-48e8-89e1-7ff1c71df81b"
        },
        "config" : {
          "items" : [ {
            "name" : "oom_heap_dump_dir",
            "value" : "/disco2/tmp",
            "sensitive" : false
          }, {
            "name" : "role_jceks_password",
            "value" : "8pyo5n9fue5y8erdmefa2z6ov",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-HIVESERVER2-BASE"
        }
      } ],
      "displayName" : "Hive",
      "roleConfigGroups" : [ {
        "name" : "hive-GATEWAY-BASE",
        "displayName" : "Gateway Default Group",
        "roleType" : "GATEWAY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hive"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-BASE",
        "displayName" : "Hive Metastore Server Default Group",
        "roleType" : "HIVEMETASTORE",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hive"
        },
        "config" : {
          "items" : [ {
            "name" : "hive_metastore_server_max_message_size",
            "value" : "858993459",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-BASE",
        "displayName" : "HiveServer2 Default Group",
        "roleType" : "HIVESERVER2",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hive"
        },
        "config" : {
          "items" : [ {
            "name" : "hiveserver2_enable_impersonation",
            "value" : "false",
            "sensitive" : false
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641",
            "sensitive" : false
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "6",
            "sensitive" : false
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "10390654156",
            "sensitive" : false
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102",
            "sensitive" : false
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "1748",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "hive-WEBHCAT-BASE",
        "displayName" : "WebHCat Server Default Group",
        "roleType" : "WEBHCAT",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hive"
        },
        "config" : {
          "items" : [ ]
        }
      } ],
      "replicationSchedules" : [ ]
    }, {
      "name" : "impala",
      "type" : "IMPALA",
      "config" : {
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs",
          "sensitive" : false
        }, {
          "name" : "hive_service",
          "value" : "hive",
          "sensitive" : false
        }, {
          "name" : "llama_am_ha_zk_auth_secret_key",
          "value" : "9tg0uoIc2TjHL4Kf3UpVoyeBgBxDIP",
          "sensitive" : true
        }, {
          "name" : "rm_dirty",
          "value" : "true",
          "sensitive" : false
        }, {
          "name" : "sentry_service",
          "value" : "sentry",
          "sensitive" : false
        } ]
      },
      "roles" : [ {
        "name" : "impala-CATALOGSERVER-b405929b0cf89b7528ef3250eb78693b",
        "type" : "CATALOGSERVER",
        "hostRef" : {
          "hostId" : "372e1e1a-7511-48e8-89e1-7ff1c71df81b"
        },
        "config" : {
          "items" : [ {
            "name" : "oom_heap_dump_dir",
            "value" : "/disco2/tmp",
            "sensitive" : false
          }, {
            "name" : "role_jceks_password",
            "value" : "9l7ys8nh42iq7q7bhgxkzzi1b",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "impala-CATALOGSERVER-BASE"
        }
      }, {
        "name" : "impala-IMPALAD-249c706dfbdf343dfea28b0188d112c9",
        "type" : "IMPALAD",
        "hostRef" : {
          "hostId" : "3192d069-25c9-4a6d-b3c8-77ee1d380856"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "avr7tcwk3mvtif4y6r1n8xcvw",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "impala-IMPALAD-BASE"
        }
      }, {
        "name" : "impala-IMPALAD-8c7c310713f5bea96630dcbe92535bb2",
        "type" : "IMPALAD",
        "hostRef" : {
          "hostId" : "5a75aa6c-6e01-454a-81a0-943ad8619b5d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4oke0fsarfbgyu6m3wqsjf9f6",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "impala-IMPALAD-BASE"
        }
      }, {
        "name" : "impala-IMPALAD-eff6992d50eb43f0a40d7a213270f7c3",
        "type" : "IMPALAD",
        "hostRef" : {
          "hostId" : "78f0a267-18ca-4aeb-93e9-a61ea942350c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7gthvo60sv8per4vr2baco46q",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "impala-IMPALAD-BASE"
        }
      }, {
        "name" : "impala-STATESTORE-b405929b0cf89b7528ef3250eb78693b",
        "type" : "STATESTORE",
        "hostRef" : {
          "hostId" : "372e1e1a-7511-48e8-89e1-7ff1c71df81b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ewyhscqwc8926apcdopag9554",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "impala-STATESTORE-BASE"
        }
      } ],
      "displayName" : "Impala",
      "roleConfigGroups" : [ {
        "name" : "impala-CATALOGSERVER-BASE",
        "displayName" : "Impala Catalog Server Default Group",
        "roleType" : "CATALOGSERVER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "impala"
        },
        "config" : {
          "items" : [ {
            "name" : "catalogd_embedded_jvm_heapsize",
            "value" : "1207959552",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "impala-IMPALAD-BASE",
        "displayName" : "Impala Daemon Default Group",
        "roleType" : "IMPALAD",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "impala"
        },
        "config" : {
          "items" : [ {
            "name" : "impalad_memory_limit",
            "value" : "268435456",
            "sensitive" : false
          }, {
            "name" : "scratch_dirs",
            "value" : "/disco1/impala/impalad,/disco2/impala/impalad",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "impala-LLAMA-BASE",
        "displayName" : "Impala Llama ApplicationMaster Default Group",
        "roleType" : "LLAMA",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "impala"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "impala-STATESTORE-BASE",
        "displayName" : "Impala StateStore Default Group",
        "roleType" : "STATESTORE",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "impala"
        },
        "config" : {
          "items" : [ ]
        }
      } ]
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "items" : [ {
          "name" : "hive_service",
          "value" : "hive",
          "sensitive" : false
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn",
          "sensitive" : false
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper",
          "sensitive" : false
        } ]
      },
      "roles" : [ {
        "name" : "oozie-OOZIE_SERVER-b405929b0cf89b7528ef3250eb78693b",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "372e1e1a-7511-48e8-89e1-7ff1c71df81b"
        },
        "config" : {
          "items" : [ {
            "name" : "oom_heap_dump_dir",
            "value" : "/disco2/tmp",
            "sensitive" : false
          }, {
            "name" : "role_jceks_password",
            "value" : "8mapnzecn03znnz3izwe30lsf",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "oozie-OOZIE_SERVER-BASE"
        }
      } ],
      "displayName" : "Oozie",
      "roleConfigGroups" : [ {
        "name" : "oozie-OOZIE_SERVER-BASE",
        "displayName" : "Oozie Server Default Group",
        "roleType" : "OOZIE_SERVER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "oozie"
        },
        "config" : {
          "items" : [ {
            "name" : "oozie_data_dir",
            "value" : "/disco2/var/lib/oozie/data",
            "sensitive" : false
          }, {
            "name" : "oozie_database_host",
            "value" : "ip-172-31-26-69.us-east-2.compute.internal",
            "sensitive" : false
          }, {
            "name" : "oozie_database_password",
            "value" : "oozie_password",
            "sensitive" : true
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql",
            "sensitive" : false
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie",
            "sensitive" : false
          }, {
            "name" : "oozie_java_heapsize",
            "value" : "52428800",
            "sensitive" : false
          } ]
        }
      } ]
    }, {
      "name" : "sentry",
      "type" : "SENTRY",
      "config" : {
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs",
          "sensitive" : false
        }, {
          "name" : "sentry_server_database_host",
          "value" : "ip-172-31-26-69.us-east-2.compute.internal",
          "sensitive" : false
        }, {
          "name" : "sentry_server_database_password",
          "value" : "sentry_password",
          "sensitive" : true
        }, {
          "name" : "sentry_service_admin_group",
          "value" : "hive,impala,hue,solr,kafka,admin",
          "sensitive" : false
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper",
          "sensitive" : false
        } ]
      },
      "roles" : [ {
        "name" : "sentry-GATEWAY-8c7c310713f5bea96630dcbe92535bb2",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "5a75aa6c-6e01-454a-81a0-943ad8619b5d"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "sentry-GATEWAY-BASE"
        }
      }, {
        "name" : "sentry-SENTRY_SERVER-249c706dfbdf343dfea28b0188d112c9",
        "type" : "SENTRY_SERVER",
        "hostRef" : {
          "hostId" : "3192d069-25c9-4a6d-b3c8-77ee1d380856"
        },
        "config" : {
          "items" : [ {
            "name" : "heap_dump_directory_free_space_absolute_thresholds",
            "value" : "{\"warning\":3221225472,\"critical\":1073741824}",
            "sensitive" : false
          }, {
            "name" : "role_jceks_password",
            "value" : "2s4uc0vwm0kn3u369l5h4bfxi",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "sentry-SENTRY_SERVER-BASE"
        }
      } ],
      "displayName" : "Sentry",
      "roleConfigGroups" : [ {
        "name" : "sentry-GATEWAY-BASE",
        "displayName" : "Gateway Default Group",
        "roleType" : "GATEWAY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "sentry"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "sentry-SENTRY_SERVER-BASE",
        "displayName" : "Sentry Server Default Group",
        "roleType" : "SENTRY_SERVER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "sentry"
        },
        "config" : {
          "items" : [ {
            "name" : "sentry_server_java_heapsize",
            "value" : "268435456",
            "sensitive" : false
          } ]
        }
      } ]
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "items" : [ {
          "name" : "database_host",
          "value" : "ip-172-31-26-69.us-east-2.compute.internal",
          "sensitive" : false
        }, {
          "name" : "database_password",
          "value" : "hue_password",
          "sensitive" : true
        }, {
          "name" : "database_type",
          "value" : "mysql",
          "sensitive" : false
        }, {
          "name" : "hive_service",
          "value" : "hive",
          "sensitive" : false
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-HTTPFS-8c7c310713f5bea96630dcbe92535bb2",
          "sensitive" : false
        }, {
          "name" : "impala_service",
          "value" : "impala",
          "sensitive" : false
        }, {
          "name" : "oozie_service",
          "value" : "oozie",
          "sensitive" : false
        }, {
          "name" : "sentry_service",
          "value" : "sentry",
          "sensitive" : false
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper",
          "sensitive" : false
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-b405929b0cf89b7528ef3250eb78693b",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "372e1e1a-7511-48e8-89e1-7ff1c71df81b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "f0h5dyk98yala51bt20jed1gt",
            "sensitive" : true
          }, {
            "name" : "secret_key",
            "value" : "kh8gN3QumoWzr7lX1mDTIuOixs5pAD",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hue-HUE_SERVER-BASE"
        }
      }, {
        "name" : "hue-KT_RENEWER-b405929b0cf89b7528ef3250eb78693b",
        "type" : "KT_RENEWER",
        "hostRef" : {
          "hostId" : "372e1e1a-7511-48e8-89e1-7ff1c71df81b"
        },
        "config" : {
          "items" : [ {
            "name" : "process_auto_restart",
            "value" : "true",
            "sensitive" : false
          }, {
            "name" : "role_jceks_password",
            "value" : "4q8wgl0xyf194whcvwkhy1v5m",
            "sensitive" : true
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hue-KT_RENEWER-BASE"
        }
      } ],
      "displayName" : "Hue",
      "roleConfigGroups" : [ {
        "name" : "hue-HUE_LOAD_BALANCER-BASE",
        "displayName" : "Balancer de carga Default Group",
        "roleType" : "HUE_LOAD_BALANCER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hue"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hue-HUE_SERVER-BASE",
        "displayName" : "Hue Server Default Group",
        "roleType" : "HUE_SERVER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hue"
        },
        "config" : {
          "items" : [ {
            "name" : "hue_http_port",
            "value" : "18888",
            "sensitive" : false
          } ]
        }
      }, {
        "name" : "hue-KT_RENEWER-BASE",
        "displayName" : "Kerberos Ticket Renewer Default Group",
        "roleType" : "KT_RENEWER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hue"
        },
        "config" : {
          "items" : [ ]
        }
      } ]
    } ],
    "parcels" : [ {
      "product" : "CDH",
      "version" : "5.11.2-1.cdh5.11.2.p0.4",
      "stage" : "DISTRIBUTED",
      "clusterRef" : {
        "clusterName" : "cluster"
      }
    }, {
      "product" : "CDH",
      "version" : "5.11.2-1.cdh5.11.2.p0.4",
      "stage" : "ACTIVATED",
      "clusterRef" : {
        "clusterName" : "cluster"
      }
    } ],
    "uuid" : "e50c9d7e-dbb3-4442-b0e2-4db1b2a2eb2f"
  } ],
  "hosts" : [ {
    "hostId" : "372e1e1a-7511-48e8-89e1-7ff1c71df81b",
    "ipAddress" : "172.31.26.220",
    "hostname" : "ip-172-31-26-220.us-east-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ {
        "name" : "memory_overcommit_threshold",
        "value" : "0.9",
        "sensitive" : false
      } ]
    }
  }, {
    "hostId" : "3192d069-25c9-4a6d-b3c8-77ee1d380856",
    "ipAddress" : "172.31.26.27",
    "hostname" : "ip-172-31-26-27.us-east-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ {
        "name" : "memory_overcommit_threshold",
        "value" : "0.9",
        "sensitive" : false
      } ]
    }
  }, {
    "hostId" : "78f0a267-18ca-4aeb-93e9-a61ea942350c",
    "ipAddress" : "172.31.26.66",
    "hostname" : "ip-172-31-26-66.us-east-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ {
        "name" : "memory_overcommit_threshold",
        "value" : "0.9",
        "sensitive" : false
      } ]
    }
  }, {
    "hostId" : "98aa182d-7ea8-49c8-b4fa-aae80ebb595b",
    "ipAddress" : "172.31.26.69",
    "hostname" : "ip-172-31-26-69.us-east-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ {
        "name" : "memory_overcommit_threshold",
        "value" : "0.9",
        "sensitive" : false
      } ]
    }
  }, {
    "hostId" : "5a75aa6c-6e01-454a-81a0-943ad8619b5d",
    "ipAddress" : "172.31.28.197",
    "hostname" : "ip-172-31-28-197.us-east-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ {
        "name" : "memory_overcommit_threshold",
        "value" : "0.9",
        "sensitive" : false
      } ]
    }
  } ],
  "users" : [ {
    "name" : "DKvothe",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "4931afb858c88a78d368cb1c8c154e828fe7c515e1239c37a587cad64f441a82",
    "pwSalt" : 8273798028491547220,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__12f66dcf-f657-4cb9-ad80-76a2ea761cc3",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "84dc9a1a528d683f7b6b42b913c77278b99f80c1d9abad639c8e261cec32294a",
    "pwSalt" : 405815511347291236,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-ACTIVITYMONITOR-409f1ca0270dfac38128d7d807063fba",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "0e620bda55e278d50f3d4022b6459e446a2897074df0a03bb0ab48a7a3127f73",
    "pwSalt" : 5432552714679627370,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-409f1ca0270dfac38128d7d807063fba",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "40989973cf0b7089c546fa463418f0dfc9c715c69b3a0f1441c772db5d1f1dc4",
    "pwSalt" : 1023566872981071034,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-409f1ca0270dfac38128d7d807063fba",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "4bb6610437a0cb551f3b97a37b284d815bdb9bc229ee607e12f8c8b4a8900698",
    "pwSalt" : -2922067104075304894,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-409f1ca0270dfac38128d7d807063fba",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "acbacff18f9330441fe3041800ef3e2fd8816a2a2b13f89d495acf5ba558b389",
    "pwSalt" : -8254613686152496075,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-409f1ca0270dfac38128d7d807063fba",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "bcea06cfe0c97a25ca527db18dddec1bc23b8ea3d596eee5fd9e79734297bd7f",
    "pwSalt" : -7539649256784712032,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "a01404e03963b6f02ffb7fb066c7cc88377b8e8a4a7f85916aadc663adb89873",
    "pwSalt" : 2165144811252900968,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "ce2f61c8305c9b591c2302f12ceb1f3b1296d36e2df5789ec264e4a7a8c6497e",
    "pwSalt" : 5694946589987752671,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.11.2",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20170811-0014",
    "gitHash" : "3c3ea33a12076fb83a8f11c4452c52fac685d01b",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ACTIVITYMONITOR-409f1ca0270dfac38128d7d807063fba",
      "type" : "ACTIVITYMONITOR",
      "hostRef" : {
        "hostId" : "98aa182d-7ea8-49c8-b4fa-aae80ebb595b"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "ael0i53qif35lmx1xhhnwrx9z",
          "sensitive" : true
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-ACTIVITYMONITOR-BASE"
      }
    }, {
      "name" : "mgmt-ALERTPUBLISHER-409f1ca0270dfac38128d7d807063fba",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "98aa182d-7ea8-49c8-b4fa-aae80ebb595b"
      },
      "config" : {
        "items" : [ {
          "name" : "heap_dump_directory_free_space_absolute_thresholds",
          "value" : "{\"warning\":2684354560,\"critical\":1572864000}",
          "sensitive" : false
        }, {
          "name" : "role_jceks_password",
          "value" : "7ydvxfzju20dki4po64pv75l8",
          "sensitive" : true
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-ALERTPUBLISHER-BASE"
      }
    }, {
      "name" : "mgmt-EVENTSERVER-409f1ca0270dfac38128d7d807063fba",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "98aa182d-7ea8-49c8-b4fa-aae80ebb595b"
      },
      "config" : {
        "items" : [ {
          "name" : "eventserver_index_directory_free_space_absolute_thresholds",
          "value" : "{\"warning\":2684354560,\"critical\":1572864000}",
          "sensitive" : false
        }, {
          "name" : "heap_dump_directory_free_space_absolute_thresholds",
          "value" : "{\"warning\":2684354560,\"critical\":1572864000}",
          "sensitive" : false
        }, {
          "name" : "role_jceks_password",
          "value" : "a99a3xqo8r5ewm8t3tf1vzqdt",
          "sensitive" : true
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-EVENTSERVER-BASE"
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-409f1ca0270dfac38128d7d807063fba",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "98aa182d-7ea8-49c8-b4fa-aae80ebb595b"
      },
      "config" : {
        "items" : [ {
          "name" : "firehose_storage_dir",
          "value" : "/disco2/var/lib/cloudera-host-monitor",
          "sensitive" : false
        }, {
          "name" : "firehose_storage_directory_free_space_absolute_thresholds",
          "value" : "{\"warning\":2684354560,\"critical\":1572864000}",
          "sensitive" : false
        }, {
          "name" : "heap_dump_directory_free_space_absolute_thresholds",
          "value" : "{\"warning\":2684354560,\"critical\":1572864000}",
          "sensitive" : false
        }, {
          "name" : "role_jceks_password",
          "value" : "b5nezmpgkdic61wmit9z6g7qd",
          "sensitive" : true
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-HOSTMONITOR-BASE"
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-409f1ca0270dfac38128d7d807063fba",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "98aa182d-7ea8-49c8-b4fa-aae80ebb595b"
      },
      "config" : {
        "items" : [ {
          "name" : "headlamp_scratch_dir",
          "value" : "/disco2/var/lib/cloudera-scm-headlamp",
          "sensitive" : false
        }, {
          "name" : "heap_dump_directory_free_space_absolute_thresholds",
          "value" : "{\"warning\":2684354560,\"critical\":1572864000}",
          "sensitive" : false
        }, {
          "name" : "reportsmanager_scratch_directory_free_space_absolute_thresholds",
          "value" : "{\"warning\":2684354560,\"critical\":1572864000}",
          "sensitive" : false
        }, {
          "name" : "role_jceks_password",
          "value" : "7x8qi78vw7l4dcaq2nw1004sz",
          "sensitive" : true
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-REPORTSMANAGER-BASE"
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-409f1ca0270dfac38128d7d807063fba",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "98aa182d-7ea8-49c8-b4fa-aae80ebb595b"
      },
      "config" : {
        "items" : [ {
          "name" : "firehose_storage_dir",
          "value" : "/disco2/var/lib/cloudera-service-monitor",
          "sensitive" : false
        }, {
          "name" : "firehose_storage_directory_free_space_absolute_thresholds",
          "value" : "{\"warning\":2147483648,\"critical\":1604321280}",
          "sensitive" : false
        }, {
          "name" : "heap_dump_directory_free_space_absolute_thresholds",
          "value" : "{\"warning\":2147483648,\"critical\":1572864000}",
          "sensitive" : false
        }, {
          "name" : "role_jceks_password",
          "value" : "8jke4j80rsvtl492xtjhltcw6",
          "sensitive" : true
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-SERVICEMONITOR-BASE"
      }
    } ],
    "displayName" : "Cloudera Management Service",
    "roleConfigGroups" : [ {
      "name" : "mgmt-ACTIVITYMONITOR-BASE",
      "displayName" : "Activity Monitor Default Group",
      "roleType" : "ACTIVITYMONITOR",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ {
          "name" : "firehose_database_host",
          "value" : "ip-172-31-26-69.us-east-2.compute.internal",
          "sensitive" : false
        }, {
          "name" : "firehose_database_name",
          "value" : "amon",
          "sensitive" : false
        }, {
          "name" : "firehose_database_password",
          "value" : "amon_password",
          "sensitive" : true
        }, {
          "name" : "firehose_database_user",
          "value" : "amon",
          "sensitive" : false
        }, {
          "name" : "oom_heap_dump_dir",
          "value" : "/disco2/tmp",
          "sensitive" : false
        } ]
      }
    }, {
      "name" : "mgmt-ALERTPUBLISHER-BASE",
      "displayName" : "Alert Publisher Default Group",
      "roleType" : "ALERTPUBLISHER",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ {
          "name" : "oom_heap_dump_dir",
          "value" : "/disco2/tmp",
          "sensitive" : false
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-BASE",
      "displayName" : "Event Server Default Group",
      "roleType" : "EVENTSERVER",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ {
          "name" : "eventserver_index_dir",
          "value" : "/disco2/var/lib/cloudera-scm-eventserver",
          "sensitive" : false
        }, {
          "name" : "oom_heap_dump_dir",
          "value" : "/disco2/tmp",
          "sensitive" : false
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-BASE",
      "displayName" : "Host Monitor Default Group",
      "roleType" : "HOSTMONITOR",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736",
          "sensitive" : false
        }, {
          "name" : "oom_heap_dump_dir",
          "value" : "/disco2/tmp",
          "sensitive" : false
        } ]
      }
    }, {
      "name" : "mgmt-NAVIGATOR-BASE",
      "displayName" : "Navigator Audit Server Default Group",
      "roleType" : "NAVIGATOR",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ {
          "name" : "oom_heap_dump_dir",
          "value" : "/disco2/tmp",
          "sensitive" : false
        } ]
      }
    }, {
      "name" : "mgmt-NAVIGATORMETASERVER-BASE",
      "displayName" : "Navigator Metadata Server Default Group",
      "roleType" : "NAVIGATORMETASERVER",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ {
          "name" : "oom_heap_dump_dir",
          "value" : "/disco2/tmp",
          "sensitive" : false
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-BASE",
      "displayName" : "Reports Manager Default Group",
      "roleType" : "REPORTSMANAGER",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "ip-172-31-26-69.us-east-2.compute.internal",
          "sensitive" : false
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman",
          "sensitive" : false
        }, {
          "name" : "headlamp_database_password",
          "value" : "rman_password",
          "sensitive" : true
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman",
          "sensitive" : false
        }, {
          "name" : "oom_heap_dump_dir",
          "value" : "/disco2/tmp",
          "sensitive" : false
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-BASE",
      "displayName" : "Service Monitor Default Group",
      "roleType" : "SERVICEMONITOR",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736",
          "sensitive" : false
        }, {
          "name" : "oom_heap_dump_dir",
          "value" : "/disco2/tmp",
          "sensitive" : false
        } ]
      }
    }, {
      "name" : "mgmt-TELEMETRYPUBLISHER-BASE",
      "displayName" : "Telemetry Publisher Default Group",
      "roleType" : "TELEMETRYPUBLISHER",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ ]
      }
    } ]
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "AD_USE_SIMPLE_AUTH",
      "value" : "false",
      "sensitive" : false
    }, {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/25/2012 15:30",
      "sensitive" : false
    }, {
      "name" : "KDC_ADMIN_PASSWORD",
      "value" : "BQIAAABFAAIAC0RLVk9USEUuQ09NAAxjbG91ZGVyYS1zY20ABWFkbWluAAAAAVnVFbcBABcAEOiX/BhZDvIkN04fZL/YVbUAAAAB",
      "sensitive" : true
    }, {
      "name" : "KDC_ADMIN_USER",
      "value" : "cloudera-scm/admin@DKVOTHE.COM",
      "sensitive" : false
    }, {
      "name" : "KDC_HOST",
      "value" : "ip-172-31-26-69.us-east-2.compute.internal",
      "sensitive" : false
    }, {
      "name" : "KRB_ENC_TYPES",
      "value" : "arcfour-hmac",
      "sensitive" : false
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD",
      "sensitive" : false
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh5/parcels/{latest_supported}/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,https://archive.cloudera.com/navigator-keytrustee5/parcels/latest/,http://archive.cloudera.com/kudu/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/",
      "sensitive" : false
    }, {
      "name" : "SECURITY_REALM",
      "value" : "DKVOTHE.COM",
      "sensitive" : false
    } ]
  },
  "allHostsConfig" : {
    "items" : [ {
      "name" : "rm_enabled",
      "value" : "true",
      "sensitive" : false
    } ]
  },
  "peers" : [ {
    "name" : "AndreCruzat",
    "type" : "REPLICATION",
    "url" : "http://ec2-18-222-1-27.us-east-2.compute.amazonaws.com:7180",
    "username" : "__cloudera_internal_user__a108c58b-3539-44e0-83a7-b4d6e26ec22b",
    "password" : "6f58389a-21a8-4ec2-9628-7d0f47b41ca07676ac7a-9018-4749-a1b8-0de5241c8283",
    "clouderaManagerCreatedUser" : true
  } ],
  "hostTemplates" : {
    "items" : [ ]
  }
}
