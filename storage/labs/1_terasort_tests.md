# HDFS testing

## make linux user
```
sudo useradd krisgeus
```

## make user directory
```
sudo -u hdfs hdfs dfs -mkdir /user/krisgeus
```

## ownership of the  user directory
```
sudo -u hdfs hdfs dfs -chown krisgeus:krisgeus /user/krisgeus
```

## generate 10Gb data

```
# convert 10GB to teragen rows
echo "(10*1024^3)/100" | bc
```
```
sudo -u krisgeus time yarn jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar teragen -Ddfs.block.size=33554432 -Dmapreduce.job.maps=4 -Dmapred.map.tasks.speculative.execution=false 107374182 teragen10G
```

output

```
17/06/06 10:27:45 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=488492
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=344
		HDFS: Number of bytes written=10737418200
		HDFS: Number of read operations=16
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=8
	Job Counters 
		Launched map tasks=4
		Other local map tasks=4
		Total time spent by all maps in occupied slots (ms)=457189
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=457189
		Total vcore-seconds taken by all map tasks=457189
		Total megabyte-seconds taken by all map tasks=468161536
	Map-Reduce Framework
		Map input records=107374182
		Map output records=107374182
		Input split bytes=344
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=1456
		CPU time spent (ms)=169130
		Physical memory (bytes) snapshot=735428608
		Virtual memory (bytes) snapshot=6336593920
		Total committed heap usage (bytes)=832045056
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=230593859918397906
	File Input Format Counters 
		Bytes Read=0
	File Output Format Counters 
		Bytes Written=10737418200
6.05user 0.32system 2:07.93elapsed 4%CPU (0avgtext+0avgdata 220156maxresident)k
0inputs+1976outputs (0major+70187minor)pagefaults 0swaps
```
## sort the data
```
sudo -u krisgeus sh -c "time yarn jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar terasort teragen10G terasort10G"
```

output 
 
```
17/06/06 10:38:18 INFO mapreduce.Job: Counters: 49
	File System Counters
		FILE: Number of bytes read=4774500483
		FILE: Number of bytes written=9477913940
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=10737468760
		HDFS: Number of bytes written=10737418200
		HDFS: Number of read operations=984
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=16
	Job Counters 
		Launched map tasks=320
		Launched reduce tasks=8
		Data-local map tasks=320
		Total time spent by all maps in occupied slots (ms)=2686319
		Total time spent by all reduces in occupied slots (ms)=910614
		Total time spent by all map tasks (ms)=2686319
		Total time spent by all reduce tasks (ms)=910614
		Total vcore-seconds taken by all map tasks=2686319
		Total vcore-seconds taken by all reduce tasks=910614
		Total megabyte-seconds taken by all map tasks=2750790656
		Total megabyte-seconds taken by all reduce tasks=932468736
	Map-Reduce Framework
		Map input records=107374182
		Map output records=107374182
		Map output bytes=10952166564
		Map output materialized bytes=4662863455
		Input split bytes=50560
		Combine input records=0
		Combine output records=0
		Reduce input groups=107374182
		Reduce shuffle bytes=4662863455
		Reduce input records=107374182
		Reduce output records=107374182
		Spilled Records=214748364
		Shuffled Maps =2560
		Failed Shuffles=0
		Merged Map outputs=2560
		GC time elapsed (ms)=38039
		CPU time spent (ms)=1533260
		Physical memory (bytes) snapshot=156930060288
		Virtual memory (bytes) snapshot=519276515328
		Total committed heap usage (bytes)=184487510016
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters 
		Bytes Read=10737418200
	File Output Format Counters 
		Bytes Written=10737418200
17/06/06 10:38:18 INFO terasort.TeraSort: done

real	6m5.751s
user	0m9.477s
sys	0m0.390s
```