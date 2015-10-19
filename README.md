# Apache Cassandra installer

This role installs Apache Cassandra

## The following changes to the standard Cassandra delivery has been made:

* G1GC used
* RAM amount can be provided in GB or in node memory percent
* runit supervisor used to run cassandra

## The following variables could be used to control the install:

variable name | default value | comment
------------- | ------------- | -------
cassandra_version | 2.1.9 | version to be installed, could also be ```latest``` for Latest release or ```stable``` for Stable release
cassandra_version_sha1 | c7fc9a9c892ec5e8bb5a52c6d15cb89234418e04 | SHA1 checksum to check the downloaded file, autodetected if version is set to ```latest``` or ```stable```
cassandra_user | cassandra | user the cassandra will be running with
cassandra_cluster_name | cassandra | cluster name
cassandra_cluster_group_name | cassandra | the name on the inventory group contains the cluster hosts. used to get seeds addresses
cassandra_path_install | /opt | path the cassanda will be installed
cassandra_path_data | ["/opt/cassandra-data/data"] | array of paths the cassanda will store data in
cassandra_path_logs | /opt/cassandra-data/logs | path the cassanda will store logs
cassandra_path_caches | /opt/cassandra-data/caches | path the cassanda will store caches
cassandra_start | cassandra-autoconfig | cassandra start script
cassandra_kill | java | program to be killed to restart cassandra
cassandra_runit | cassandra | runit service name
cassandra_node_iface_ext | eth0 | external network interface name
cassandra_node_iface_int | eth0 | internal network interface name
cassandra_mem_gb | 0 | RAM available to cassandra in GB
cassandra_mem_pc | 50 | RAM available to cassandra in percent. Ignored if cassandra_mem_gb provided

## Dependencies:

* java: https://github.com/gitinsky/ansible-role-java
* runit: https://github.com/gitinsky/ansible-role-runit


