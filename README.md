Galera Cluster monitoring template for Zabbix
===========================================


Tested on Zabbix Version 3.2

See at [share.zabbix.com](https://share.zabbix.com/databases/mysql/galera-cluster-monitoring)

FEATURES
--------
* Monitoring of Cluster Status, Replicated Data, Send/Recieve Queue, and more
* Graph showing Replication Statistics
* Triggers for Cluster State and Cluster Member problems


REQUIREMENTS
------------
* Zabbix server version 3.2
* Galera Cluster installed
* Account with proper permissions to query WSREP stats

INSTALLATION
------------
* Agent
  * Copy __userparameter_galera.conf__ to __/etc/zabbix/zabbix_agentd.d/userparameter_galera.conf__
  * Restart zabbix_agent
* Server
  * Import template __App-Galera_Cluster__ file
  * Add Value Mapping Information

Testing
-------
To test that everything works use the `zabbix_agentd -t` to query the statistics :

```bash
# view size of the cluster
zabbix_agentd -t "galera.cluster_size"
# view status of the cluster
zabbix_agentd -t "galera.cluster_status"
```

AUTHOR
------
MogiePete

LICENSE
-------
GNU GENERAL PUBLIC LICENSE Version 3, 29 June 2007
