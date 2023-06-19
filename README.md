# stress-profile
Simple cassandra-stress profile, simulating a time-series kind of use case.

To ingest the initial data set:

```shell
cassandra-stress user profile=file:///profile.yml no-warmup 'ops(insert=1)' n=1000000 -rate threads=8 -node <node IP>
```

To run a mixed workload:

```
cassandra-stress user profile=file:///profile.yml no-warmup 'ops(insert=10, read-latest=10, scan-partition=1)' n=1000000 -rate threads=8 -node <node IP>
```
