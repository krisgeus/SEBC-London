## What's the status of hive
```
curl -u krisgeus -X GET http://54.77.56.201:7180/api/v2/clusters/krisgeus/services/hive
```

Output:

```
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-172-31-5-114.eu-west-1.compute.internal:7180/cmf/serviceRedirect/hive",
  "serviceState" : "STARTED",
  "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD"
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD"
  } ],
  "configStale" : false,
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive"
}
```

## Stop Hive
```
curl -u krisgeus -X POST http://54.77.56.201:7180/api/v2/clusters/krisgeus/services/hive/commands/stop
```

Output:

```
{
  "id" : 774,
  "name" : "Stop",
  "startTime" : "2017-06-07T13:22:01.187Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}
```

### See status of the command
```
curl -u krisgeus -X GET http://54.77.56.201:7180/api/v2/commands/774
```

Output:

```
{
  "id" : 774,
  "name" : "Stop",
  "startTime" : "2017-06-07T13:22:01.187Z",
  "endTime" : "2017-06-07T13:22:14.425Z",
  "active" : false,
  "success" : true,
  "resultMessage" : "Successfully stopped service.",
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  },
  "children" : {
    "items" : [ {
      "id" : 775,
      "name" : "Stop",
      "startTime" : "2017-06-07T13:22:01.190Z",
      "endTime" : "2017-06-07T13:22:14.425Z",
      "active" : false,
      "success" : true,
      "resultMessage" : "Successfully stopped process.",
      "serviceRef" : {
        "clusterName" : "cluster",
        "serviceName" : "hive"
      },
      "roleRef" : {
        "clusterName" : "cluster",
        "serviceName" : "hive",
        "roleName" : "hive-HIVESERVER2-37e71e40b4d9e946485f34620f27d372"
      }
    }, {
      "id" : 776,
      "name" : "Stop",
      "startTime" : "2017-06-07T13:22:01.191Z",
      "endTime" : "2017-06-07T13:22:14.422Z",
      "active" : false,
      "success" : true,
      "resultMessage" : "Successfully stopped process.",
      "serviceRef" : {
        "clusterName" : "cluster",
        "serviceName" : "hive"
      },
      "roleRef" : {
        "clusterName" : "cluster",
        "serviceName" : "hive",
        "roleName" : "hive-HIVEMETASTORE-37e71e40b4d9e946485f34620f27d372"
      }
    } ]
  }
}
```
## Start hive
```
curl -u krisgeus -X POST http://54.77.56.201:7180/api/v2/clusters/krisgeus/services/hive/commands/start
```

Output:

```
{
  "id" : 778,
  "name" : "Start",
  "startTime" : "2017-06-07T13:24:50.095Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}
```
