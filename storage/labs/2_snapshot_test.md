# Snapshotting HDFS

## create the precious directory

```
sudo -u krisgeus hdfs dfs -mkdir precious
```

## Copy the course zip file into it

First scp it to a cluster machine

```
scp -i "sebc.pem" SEBC-master.zip ec2-user@34.253.155.59:/tmp/
```

then add it to HDFS

```
sudo -u krisgeus hdfs dfs -put /tmp/SEBC-master.zip precious/
```

## Enable snapshotting

```
sudo -u hdfs hdfs dfsadmin -allowSnapshot /user/krisgeus/precious
```

This can also be done from the CM UI ;-)

## create a snapshot
```
sudo -u krisgeus hdfs dfs -createSnapshot precious sebc-hdfs-test
```

## Delete the directory
```
sudo -u krisgeus hdfs dfs -rm -r precious
```

output states directory cannot be removed recursively since it is snapshottable and has snapshots. Nice

## delete the file
```
sudo -u krisgeus hdfs dfs -rm precious/SEBC-master.zip
```

## restore the file

#### check the location of the snapshotted file
```
sudo -u krisgeus hdfs dfs -ls -R precious/.snapshot
```

#### restore is just copying
```
sudo -u krisgeus hdfs dfs -cp precious/.snapshot/sebc-hdfs-test/SEBC-master.zip precious/
```