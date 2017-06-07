### Fastest run 4 mappers, 8 reducers, 512M
```
+ for j in 1 2 4 8
+ for k in 512 1024
++ echo '(512*0.8)/1'
++ bc
+ MAP_MB=409
++ echo '(512*0.8)/1'
++ bc
+ RED_MB=409
+ /opt/cloudera/parcels/CDH/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar teragen -Dmapreduce.job.maps=4 -Dmapreduce.map.memory.mb=512 -Dmapreduce.map.java.opts.max.heap=409 53687091 results/tg-5GB-4-8-512

real	1m9.233s
user	0m6.045s
sys	0m0.261s
+ /opt/cloudera/parcels/CDH/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar terasort -Dmapreduce.job.maps=4 -Dmapreduce.job.reduces=8 -Dmapreduce.map.memory.mb=512 -Dmapreduce.map.java.opts.max.heap=409 -Dmapreduce.reduce.memory.mb=512 -Dmapreduce.reduce.java.opts.max.heap=409 results/tg-5GB-4-8-512 results/ts-5GB-4-8-512

real	1m36.341s
user	0m7.604s
sys	0m0.282s
+ /opt/cloudera/parcels/CDH/bin/hadoop fs -rm -r -skipTrash results/tg-5GB-4-8-512
Deleted results/tg-5GB-4-8-512
+ /opt/cloudera/parcels/CDH/bin/hadoop fs -rm -r -skipTrash results/ts-5GB-4-8-512
Deleted results/ts-5GB-4-8-512
```

### Slowest 4 mappers, 1 reducer, 1024M
```
+ for k in 512 1024
++ echo '(1024*0.8)/1'
++ bc
+ MAP_MB=819
++ echo '(1024*0.8)/1'
++ bc
+ RED_MB=819
+ /opt/cloudera/parcels/CDH/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar teragen -Dmapreduce.job.maps=4 -Dmapreduce.map.memory.mb=1024 -Dmapreduce.map.java.opts.max.heap=819 53687091 results/tg-5GB-4-1-1024

real	1m19.939s
user	0m5.863s
sys	0m0.231s
+ /opt/cloudera/parcels/CDH/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar terasort -Dmapreduce.job.maps=4 -Dmapreduce.job.reduces=1 -Dmapreduce.map.memory.mb=1024 -Dmapreduce.map.java.opts.max.heap=819 -Dmapreduce.reduce.memory.mb=1024 -Dmapreduce.reduce.java.opts.max.heap=819 results/tg-5GB-4-1-1024 results/ts-5GB-4-1-1024

real	2m44.556s
user	0m8.040s
sys	0m0.293s
+ /opt/cloudera/parcels/CDH/bin/hadoop fs -rm -r -skipTrash results/tg-5GB-4-1-1024
Deleted results/tg-5GB-4-1-1024
+ /opt/cloudera/parcels/CDH/bin/hadoop fs -rm -r -skipTrash results/ts-5GB-4-1-1024
Deleted results/ts-5GB-4-1-1024
```