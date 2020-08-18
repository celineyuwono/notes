## Hadoop Cluster and Extras

### Source URL: [https://www.tldp.org/HOWTO/openMosix-HOWTO/x135.html](https://www.tldp.org/HOWTO/openMosix-HOWTO/x135.html)

### Hadoop Cluster
![Hadoop Cluster Architecture](https://i.ibb.co/qWtGn1t/Screen-Shot-2020-08-18-at-11-05-03.png)
- **Computer cluster:** Collection of computers that work together and is viewed as a single system. Each node (computer) of a computer cluster is set to perform the same task, controlled and scheduled by a software.
- **Hadoop clusters** have each node set to perform the same task, controlled and schedules by the Master.

### Hadoop Extras
- Before MapReduce and Yarn are one component, but now split into two so we can customize our own MapReduce.
- **Pig:** API, SQL-style syntax without Java/Python. Pig transforms scripts that runs on MapReduce, that goes to YARN and HDFS to get the data you want.
- **Hive:** Interface, taking SQL queries and making HDFS data look like database.
- **Apache Ambari:** Sits on top of everything.
- **MESOS:** Similar to YARN, can work together with YARN.
- **Spark:** Similar to MapReduce using Java or Python, process data on Hadoop Cluster.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMzU4Mzg0NTk4XX0=
-->