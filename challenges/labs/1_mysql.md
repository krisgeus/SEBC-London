### hostname mysql node
```
hostname -f
```
output
```
ip-172-31-2-76.eu-west-1.compute.internal
```

### mysql version
```
mysql --version
```

output
```
mysql  Ver 14.14 Distrib 5.5.56, for Linux (x86_64) using readline 5.1
```

### database list
```
sudo mysql -e "SHOW DATABASES;"
```

output

```
+--------------------+
| Database           |
+--------------------+
| information_schema |
| hive               |
| hue                |
| mysql              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
| sentry             |
+--------------------+
```
