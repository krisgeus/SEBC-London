## Calling the api
```
curl -u krisgeus http://54.77.56.201:7180/api/v2/cm/deployment
```

Output:  

```
{
  "timestamp" : "2017-06-07T12:57:52.426Z",
  "clusters" : [ {
    "name" : "krisgeus",
    "version" : "CDH5",
    "services" : [ {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "639631360"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_java_heapsize",
            "value" : "639631360"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "2287940403"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "385"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "ip-172-31-10-111.eu-west-1.compute.internal"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "hive123"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-37e71e40b4d9e946485f34620f27d372",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "64e23f70-557e-4e06-b8a8-4bf1760fcc0b"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-745ec954a62f226a2661ffdc9f6798d8",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "2626de76-4fd2-449f-884a-2ca85694bb95"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-9d62d2531ba33f917513fd205d330d43",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "6d15649b-af6c-4bf9-8aa5-e7b9b7322b3c"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-d3158c844932b411114d603236184cec",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "e3cfc1aa-5f12-409e-9078-eb2e0d7820e1"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-ecc9bf119d5341156b4227bb01bb78fd",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "faae5244-79ce-46db-a56c-319066ed52b9"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-37e71e40b4d9e946485f34620f27d372",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "64e23f70-557e-4e06-b8a8-4bf1760fcc0b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9633fdnnca78qaesv8r3aqpge"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-37e71e40b4d9e946485f34620f27d372",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "64e23f70-557e-4e06-b8a8-4bf1760fcc0b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "cbmtumssqpzxu34qkjo1s7uie"
          } ]
        }
      } ],
      "displayName" : "Hive"
    }, {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "SERVER",
          "items" : [ {
            "name" : "zookeeper_server_java_heapsize",
            "value" : "639631360"
          } ]
        } ],
        "items" : [ ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-37e71e40b4d9e946485f34620f27d372",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "64e23f70-557e-4e06-b8a8-4bf1760fcc0b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "84vbre6v7185rn3yxct1u8ryd"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-745ec954a62f226a2661ffdc9f6798d8",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "2626de76-4fd2-449f-884a-2ca85694bb95"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6pvwnddhz17u5pt8i1cutie3w"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-d3158c844932b411114d603236184cec",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "e3cfc1aa-5f12-409e-9078-eb2e0d7820e1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "96dgzhkp5jqllq2ort453b5tj"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      } ],
      "displayName" : "ZooKeeper"
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "database_host",
          "value" : "ip-172-31-10-111.eu-west-1.compute.internal"
        }, {
          "name" : "database_password",
          "value" : "hue123"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-HTTPFS-9d62d2531ba33f917513fd205d330d43"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-37e71e40b4d9e946485f34620f27d372",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "64e23f70-557e-4e06-b8a8-4bf1760fcc0b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "94q9sx5xyzqqa0mm7tea30dab"
          }, {
            "name" : "secret_key",
            "value" : "nnGny0eTCJPsdgNgPzp05PklJfrGQH"
          } ]
        }
      } ],
      "displayName" : "Hue"
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "OOZIE_SERVER",
          "items" : [ {
            "name" : "oozie_database_host",
            "value" : "ip-172-31-10-111.eu-west-1.compute.internal"
          }, {
            "name" : "oozie_database_password",
            "value" : "oozie123"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
          }, {
            "name" : "oozie_java_heapsize",
            "value" : "639631360"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "oozie-OOZIE_SERVER-37e71e40b4d9e946485f34620f27d372",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "64e23f70-557e-4e06-b8a8-4bf1760fcc0b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "98pykf6rdubf4luq81hgi5rkn"
          } ]
        }
      } ],
      "displayName" : "Oozie"
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "8"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "2"
          } ]
        }, {
          "roleType" : "JOBHISTORY",
          "items" : [ {
            "name" : "mr2_jobhistory_java_heapsize",
            "value" : "639631360"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "rm_cpu_shares",
            "value" : "1800"
          }, {
            "name" : "rm_io_weight",
            "value" : "900"
          }, {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "3"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "4606"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "resource_manager_java_heapsize",
            "value" : "639631360"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "4938"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "3"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "90"
        }, {
          "name" : "yarn_service_cgroups",
          "value" : "false"
        }, {
          "name" : "yarn_service_lce_always",
          "value" : "false"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "wRA3vySHvvHMEfner51jW77OIT0kuM"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-37e71e40b4d9e946485f34620f27d372",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "64e23f70-557e-4e06-b8a8-4bf1760fcc0b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9kr47zes5txppwq1cu5rd6ag6"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-745ec954a62f226a2661ffdc9f6798d8",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "2626de76-4fd2-449f-884a-2ca85694bb95"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "d5aoob6dnysjxps0192blk7mp"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-9d62d2531ba33f917513fd205d330d43",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "6d15649b-af6c-4bf9-8aa5-e7b9b7322b3c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1q8ey1q3tcwymqhqhxxovqufs"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-d3158c844932b411114d603236184cec",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "e3cfc1aa-5f12-409e-9078-eb2e0d7820e1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bpprekopzyx68iktb868turi1"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-ecc9bf119d5341156b4227bb01bb78fd",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "faae5244-79ce-46db-a56c-319066ed52b9"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9obpzl5o1dyoomce116k3d9vd"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-37e71e40b4d9e946485f34620f27d372",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "64e23f70-557e-4e06-b8a8-4bf1760fcc0b"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "78"
          }, {
            "name" : "role_jceks_password",
            "value" : "d3047qrihowiylk3whgprsl09"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "BALANCER",
          "items" : [ {
            "name" : "balancer_java_heapsize",
            "value" : "639631360"
          } ]
        }, {
          "roleType" : "DATANODE",
          "items" : [ {
            "name" : "datanode_java_heapsize",
            "value" : "1073741824"
          }, {
            "name" : "dfs_data_dir_list",
            "value" : "/dfs/dn"
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "3219965132"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4294967296"
          }, {
            "name" : "rm_cpu_shares",
            "value" : "200"
          }, {
            "name" : "rm_io_weight",
            "value" : "100"
          } ]
        }, {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "dfs_client_use_trash",
            "value" : "true"
          } ]
        }, {
          "roleType" : "JOURNALNODE",
          "items" : [ {
            "name" : "dfs_journalnode_edits_dir",
            "value" : "/dfs/jn"
          } ]
        }, {
          "roleType" : "NAMENODE",
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          }, {
            "name" : "fs_trash_interval",
            "value" : "10"
          }, {
            "name" : "namenode_java_heapsize",
            "value" : "1073741824"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/dfs/snn"
          }, {
            "name" : "secondary_namenode_java_heapsize",
            "value" : "1073741824"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "7NwUkp8pra0n4xgVDv8PWTxQV3OrQV"
        }, {
          "name" : "dfs_ha_fencing_methods",
          "value" : "shell(true)"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "5AZ1B3yM986TSrJPkSVAv7yO8kOBQD"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "i0Q6MyT0FAmdFyBl5ocsTwVFOzBvMm"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "10"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-37e71e40b4d9e946485f34620f27d372",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "64e23f70-557e-4e06-b8a8-4bf1760fcc0b"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-745ec954a62f226a2661ffdc9f6798d8",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "2626de76-4fd2-449f-884a-2ca85694bb95"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "19uze089e9wm6bt69jazq5drl"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-9d62d2531ba33f917513fd205d330d43",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "6d15649b-af6c-4bf9-8aa5-e7b9b7322b3c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3szf32a890079kq24321ygxur"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-d3158c844932b411114d603236184cec",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "e3cfc1aa-5f12-409e-9078-eb2e0d7820e1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "nr0ll5ecvgrknxycr95zktrr"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-ecc9bf119d5341156b4227bb01bb78fd",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "faae5244-79ce-46db-a56c-319066ed52b9"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ebop1j09k0fj18xcpyouwm18p"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-37e71e40b4d9e946485f34620f27d372",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "64e23f70-557e-4e06-b8a8-4bf1760fcc0b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "b7igei51a062mpvk02t5v5xvs"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-d3158c844932b411114d603236184cec",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "e3cfc1aa-5f12-409e-9078-eb2e0d7820e1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "cdg90beicz28a7z8yajg8yjj5"
          } ]
        }
      }, {
        "name" : "hdfs-HTTPFS-9d62d2531ba33f917513fd205d330d43",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "6d15649b-af6c-4bf9-8aa5-e7b9b7322b3c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5ml1vqp2drgy1b1mh9oyia72f"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-37e71e40b4d9e946485f34620f27d372",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "64e23f70-557e-4e06-b8a8-4bf1760fcc0b"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7ugiwnal5vzo11djsd7pvbvdu"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-745ec954a62f226a2661ffdc9f6798d8",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "2626de76-4fd2-449f-884a-2ca85694bb95"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bu0yngywlu94gk9zpz94x6q21"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-d3158c844932b411114d603236184cec",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "e3cfc1aa-5f12-409e-9078-eb2e0d7820e1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "23ce7vr5fwg427t0ib9my3qrt"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-37e71e40b4d9e946485f34620f27d372",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "64e23f70-557e-4e06-b8a8-4bf1760fcc0b"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "80"
          }, {
            "name" : "role_jceks_password",
            "value" : "elf4iaib370n9x7lb1t56vqxe"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-d3158c844932b411114d603236184cec",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "e3cfc1aa-5f12-409e-9078-eb2e0d7820e1"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "86"
          }, {
            "name" : "role_jceks_password",
            "value" : "2ejxzl9lstvppa9npgijshv61"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "64e23f70-557e-4e06-b8a8-4bf1760fcc0b",
    "ipAddress" : "172.31.10.111",
    "hostname" : "ip-172-31-10-111.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "e3cfc1aa-5f12-409e-9078-eb2e0d7820e1",
    "ipAddress" : "172.31.14.122",
    "hostname" : "ip-172-31-14-122.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "2626de76-4fd2-449f-884a-2ca85694bb95",
    "ipAddress" : "172.31.3.147",
    "hostname" : "ip-172-31-3-147.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "6d15649b-af6c-4bf9-8aa5-e7b9b7322b3c",
    "ipAddress" : "172.31.3.58",
    "hostname" : "ip-172-31-3-58.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "faae5244-79ce-46db-a56c-319066ed52b9",
    "ipAddress" : "172.31.5.114",
    "hostname" : "ip-172-31-5-114.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__eb0d6464-4362-4151-abd4-a8a7d8a5f9c1",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "01673387cf9bb22865bd0f03de38b02c14fdbf78ecf8c4a6b12f585e63e67b8a",
    "pwSalt" : 2755376798908390089,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-37e71e40b4d9e946485f34620f27d372",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "e19e55473906346f1b237dce425ac44af270250b29a610e2d949e28006f9cabf",
    "pwSalt" : 521643722667601847,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-37e71e40b4d9e946485f34620f27d372",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "4b468981834b3f052d0aa59549f6a1c22cd746af02cef55b0838bb2e59f05031",
    "pwSalt" : 1093886840596284540,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-37e71e40b4d9e946485f34620f27d372",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "a6816dbdc7073432a2a6cd4fe6178f9827b0ab23c7517cc678b19ff362c51866",
    "pwSalt" : -9106357408591838500,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-37e71e40b4d9e946485f34620f27d372",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "c26145ee305582c2341371d5f67c9cc39567931bab2adc26b24a4491b9fbfbda",
    "pwSalt" : -7313489353013204261,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "9eaea136bf9bb6182b64422187bb1124914feb7cd582c49b2c9768e37f3a019e",
    "pwSalt" : 6575194850258321317,
    "pwLogin" : true
  }, {
    "name" : "krisgeus",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "a07954dcf1da620cc5961307b8a2fc53393245b65f63d1291aed7f8dc62e85f6",
    "pwSalt" : -7914094119226771958,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "36baa1dcaeba5af8e24d34f9ba8ad6de68868daedc1da456bcdc3ddfacfaeffa",
    "pwSalt" : 1848720394515296372,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.8.3",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20161019-1013",
    "gitHash" : "518f0d6d44abc87bc392646e4369a20c8192b7cf",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "roleTypeConfigs" : [ {
        "roleType" : "EVENTSERVER",
        "items" : [ {
          "name" : "event_server_heapsize",
          "value" : "639631360"
        } ]
      }, {
        "roleType" : "HOSTMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "639631360"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "831520768"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "ip-172-31-10-111.eu-west-1.compute.internal"
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_password",
          "value" : "rman123"
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman"
        }, {
          "name" : "headlamp_heapsize",
          "value" : "639631360"
        } ]
      }, {
        "roleType" : "SERVICEMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "639631360"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "831520768"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ALERTPUBLISHER-37e71e40b4d9e946485f34620f27d372",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "64e23f70-557e-4e06-b8a8-4bf1760fcc0b"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "7g43krepd6nmh0mujntorrsae"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-37e71e40b4d9e946485f34620f27d372",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "64e23f70-557e-4e06-b8a8-4bf1760fcc0b"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "afsb65671obxaom93b2mos49c"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-37e71e40b4d9e946485f34620f27d372",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "64e23f70-557e-4e06-b8a8-4bf1760fcc0b"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "dypnz7nhqby303o8jwoywpd4r"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-37e71e40b4d9e946485f34620f27d372",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "64e23f70-557e-4e06-b8a8-4bf1760fcc0b"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "9hd18a5b8psr739in8y0pa6ln"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-37e71e40b4d9e946485f34620f27d372",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "64e23f70-557e-4e06-b8a8-4bf1760fcc0b"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "5pm7dsu98izh6nvrg06ewbsaj"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/23/2012 23:40"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh5/parcels/5.8.3/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,https://archive.cloudera.com/navigator-keytrustee5/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/"
    } ]
  }
}
```