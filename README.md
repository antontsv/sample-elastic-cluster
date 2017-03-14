# Create sample Elasticsearch cluster

```sh
git clone --recursive https://github.com/antontsv/sample-elastic-cluster.git
cd sample-elastic-cluster
vagrant plugin install vagrant-cachier
vagrant up
curl 'http://10.100.100.101:9201/_cluster/health?pretty'
```

if everything is successfull you will see the following:
```json
{
  "cluster_name" : "the-one",
  "status" : "green",
  "timed_out" : false,
  "number_of_nodes" : 3,
  "number_of_data_nodes" : 3,
  "active_primary_shards" : 0,
  "active_shards" : 0,
  "relocating_shards" : 0,
  "initializing_shards" : 0,
  "unassigned_shards" : 0,
  "delayed_unassigned_shards" : 0,
  "number_of_pending_tasks" : 0,
  "number_of_in_flight_fetch" : 0,
  "task_max_waiting_in_queue_millis" : 0,
  "active_shards_percent_as_number" : 100.0
}
```
Double check cluster status says "green".

## Required software versions
🚀  This setup is verified with: Vagrant 1.9.2 and VirtualBox 5.1.14
on MacOS/Windows

🚧  Please note at the time of writing VirtualBox 5.1.16/Vagrant 1.9.2
is not working on windows - sync folder is not mounted properly
