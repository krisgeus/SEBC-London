### HDFS ls user
```
sudo -u hdfs hdfs dfs -ls /user
```

output:

```
Found 8 items
drwxr-xr-x   - admin   admin               0 2017-06-09 06:41 /user/admin
drwxr-xr-x   - hdfs    supergroup          0 2017-06-09 06:41 /user/hdfs
drwxrwxrwx   - mapred  hadoop              0 2017-06-09 06:37 /user/history
drwxrwxr-t   - hive    hive                0 2017-06-09 06:38 /user/hive
drwxrwxr-x   - hue     hue                 0 2017-06-09 06:38 /user/hue
drwxr-xr-x   - jeremy  jeremy              0 2017-06-09 06:42 /user/jeremy
drwxrwxr-x   - oozie   oozie               0 2017-06-09 06:38 /user/oozie
drwxr-xr-x   - theresa theresa             0 2017-06-09 06:42 /user/theresa
```


### Api call
```
curl -u admin -X GET http://52.19.57.45:7180/api/v14/hosts
```
output

```
{
  "items" : [ {
    "hostId" : "d6eb9928-c019-46e8-8917-113341800a32",
    "ipAddress" : "172.31.10.250",
    "hostname" : "ip-172-31-10-250.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-9-91.eu-west-1.compute.internal:7180/cmf/hostRedirect/d6eb9928-c019-46e8-8917-113341800a32",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15331930112
  }, {
    "hostId" : "3aee93be-d4da-4e11-9680-8958ce434a75",
    "ipAddress" : "172.31.14.9",
    "hostname" : "ip-172-31-14-9.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-9-91.eu-west-1.compute.internal:7180/cmf/hostRedirect/3aee93be-d4da-4e11-9680-8958ce434a75",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15331930112
  }, {
    "hostId" : "77b05ec4-520f-4bdd-bc7e-ea2e9434338d",
    "ipAddress" : "172.31.2.76",
    "hostname" : "ip-172-31-2-76.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-9-91.eu-west-1.compute.internal:7180/cmf/hostRedirect/77b05ec4-520f-4bdd-bc7e-ea2e9434338d",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15331930112
  }, {
    "hostId" : "ae8b58fe-814a-4d49-b508-6cdc2bf714bb",
    "ipAddress" : "172.31.9.10",
    "hostname" : "ip-172-31-9-10.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-9-91.eu-west-1.compute.internal:7180/cmf/hostRedirect/ae8b58fe-814a-4d49-b508-6cdc2bf714bb",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15331930112
  }, {
    "hostId" : "91f97f13-67a1-4f20-86d9-f1a4827c70a3",
    "ipAddress" : "172.31.9.91",
    "hostname" : "ip-172-31-9-91.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-9-91.eu-west-1.compute.internal:7180/cmf/hostRedirect/91f97f13-67a1-4f20-86d9-f1a4827c70a3",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15331930112
  } ]
}
```