# Replication testing

## make source directory
```
sudo su hdfs -c "hdfs dfs -mkdir /krisgeus"
```
or  
```
sudo -u hdfs hdfs dfs -mkdir /krisgeus
```

create the other custer target directory  
```
sudo -u hdfs hdfs dfs -mkdir /kaivoigt
```

## generate data

#### 500MB of data is how many rows?

Stolen from [https://gist.github.com/dstreev/4da0c9c07c8d82fc033e](https://gist.github.com/dstreev/4da0c9c07c8d82fc033e)

```
# GEN_ROWS=`echo "($VALUE*1024^$MULTIPLIER)/100" | bc

echo "(500*1024^2)/100" | bc
```
```
sudo -u hdfs yarn jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar teragen -Dmapred.map.tasks=300 -Dmapred.map.tasks.speculative.execution=false 5242880 /krisgeus/teragen
```

## distcp

### open up the cluster ports for distcp
based on [this cloudera documentation page](https://www.cloudera.com/documentation/enterprise/5-5-x/topics/install_ports_distcp.html)

open port 8020 on the namenode and 50010 on the datanodes to be accessable from outside the cluster

```
sudo -u hdfs hadoop distcp hdfs://35.176.11.210:8020/user/kaivoigt/tera500M hdfs://ip-172-31-10-111.eu-west-1.compute.internal:8020/kaivoigt/
```
generates the following output  

```
17/06/06 09:15:58 INFO tools.DistCp: Input Options: DistCpOptions{atomicCommit=false, syncFolder=false, deleteMissing=false, ignoreFailures=false, overwrite=false, skipCRC=false, blocking=true, numListstatusThreads=0, maxMaps=20, mapBandwidth=100, sslConfigurationFile='null', copyStrategy='uniformsize', preserveStatus=[], preserveRawXattrs=false, atomicWorkPath=null, logPath=null, sourceFileListing=null, sourcePaths=[hdfs://35.176.11.210:8020/user/kaivoigt/tera500M], targetPath=hdfs://ip-172-31-10-111.eu-west-1.compute.internal:8020/kaivoigt, targetPathExists=true, filtersFile='null'}
17/06/06 09:15:58 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-10-111.eu-west-1.compute.internal/172.31.10.111:8032
17/06/06 09:15:58 INFO tools.SimpleCopyListing: Paths (files+dirs) cnt = 4; dirCnt = 1
17/06/06 09:15:58 INFO tools.SimpleCopyListing: Build file listing completed.
17/06/06 09:15:58 INFO Configuration.deprecation: io.sort.mb is deprecated. Instead, use mapreduce.task.io.sort.mb
17/06/06 09:15:58 INFO Configuration.deprecation: io.sort.factor is deprecated. Instead, use mapreduce.task.io.sort.factor
17/06/06 09:15:58 INFO tools.DistCp: Number of paths in the copy list: 4
17/06/06 09:15:59 INFO tools.DistCp: Number of paths in the copy list: 4
17/06/06 09:15:59 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-10-111.eu-west-1.compute.internal/172.31.10.111:8032
17/06/06 09:15:59 INFO mapreduce.JobSubmitter: number of splits:3
17/06/06 09:15:59 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1496743842669_0002
17/06/06 09:15:59 INFO impl.YarnClientImpl: Submitted application application_1496743842669_0002
17/06/06 09:15:59 INFO mapreduce.Job: The url to track the job: http://ip-172-31-10-111.eu-west-1.compute.internal:8088/proxy/application_1496743842669_0002/
17/06/06 09:15:59 INFO tools.DistCp: DistCp job-id: job_1496743842669_0002
17/06/06 09:15:59 INFO mapreduce.Job: Running job: job_1496743842669_0002
17/06/06 09:16:04 INFO mapreduce.Job: Job job_1496743842669_0002 running in uber mode : false
17/06/06 09:16:04 INFO mapreduce.Job:  map 0% reduce 0%
17/06/06 09:16:11 INFO mapreduce.Job:  map 33% reduce 0%
17/06/06 09:16:16 INFO mapreduce.Job:  map 100% reduce 0%

```

Everytime the job get's stuck at 100% map completion.
The otherway around it gets stuck at 3%

Both are able to do a distcp internally though. 
```
sudo -u hdfs hadoop distcp /krisgeus/teragen /kaivoigt2/
```

Seems a aws networking issue. Not investigating any further

## bdr

Simple configuration from within cloudera manager. Pointing to the 7180 port and providing cm credentials.

Because cm used the internal private ip adresses the BDR job is not able to connect to the cluster.

## Check
```
hdfs fsck <path> -files -blocks
```