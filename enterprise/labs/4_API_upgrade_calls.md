### Report the latest available version of the API

```
curl -u krisgeus -X GET http://54.77.56.201:7180/api/version
```

Output:

```
v14
```


### Report the CM version 

```
curl -u krisgeus -X GET http://54.77.56.201:7180/api/v14/cm/version
```

Output:

{
  "version" : "5.9.2",
  "buildUser" : "jenkins",
  "buildTimestamp" : "20170330-1814",
  "gitHash" : "822da28bff818f57fc1bfc3eafe3a550300ef1b0",
  "snapshot" : false
}
```

```

### List all CM users

```
curl -u krisgeus -X GET http://54.77.56.201:7180/api/v14/users
```

Output:

```
{
  "items" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ]
  }, {
    "name" : "krisgeus",
    "roles" : [ "ROLE_ADMIN" ]
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ]
  } ]
}
```

### Report the database server in use by CM

```
curl -u krisgeus -X GET http://54.77.56.201:7180/api/v14/cm/scmDbInfo
```

Output:

```
{
  "scmDbType" : "MYSQL",
  "embeddedDbUsed" : false
}
```
