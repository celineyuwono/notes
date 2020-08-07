## Hadoop

### What is Hadoop?
#### [https://www.youtube.com/watch?v=9s-vSeWej1U](https://www.youtube.com/watch?v=9s-vSeWej1U)

1. Google Labs team developed an algorithm, MapReduce that allowed for large data calculations to be chopped up into smaller chunks and mapped to many computers. When the calculation is done brought back together to produce resulting data sets.
2. Hadoop is an open-source project which allows applications to run using MapReduce algorithm.
3. It is reliant on Java, but tools are being developed to help adopt Hadoop without learning Java.
4. Use Hadoop if you have big data (10TB+), statistical analysis, ETL processing, and business intelligence.


### Hadoop vs Traditional SQL Sources
#### [https://www.youtube.com/watch?v=MfF750YVDxM](https://www.youtube.com/watch?v=MfF750YVDxM)

1. Schema on Write vs Schema on Read

- With traditional SQL DB, when you transfer data from one DB to another, we have to ensure the data being transferred meets the data types the DB is expecting.
- With schema on read, when we write data into Hadoop Distributed Filing System, we just bring the data in without dictating rules. When we read the data, we apply the rules to the code that reads the data, rather than reconfiguring the structure of the data ahead of time.
- This has profound implications on how the data is stored.

2. How the data is stored

- In SQL, data is stored in logical forms like tables and columns.
- In Hadoop, data is compressed file in text or other types. Example: When data X enters Hadoop, data X is replicated across multiple nodes in HDFS. Hadoop tracks where all the copies of the data X are. This is necessary for massive scalability.

3. Hadoop is architected for an unlimited number of servers

- The structure of query in Hadoop is a Java program, which defines the request and distributes the search across all copies of data X in the HDFS. If there are 5 copies of data X in a total of 10 servers, we search all 5 copies but segments the search so that only 1/5 of data X is searched in 1 server. When process is finished, answer is reducer program in node cluster to do some processing.

4. Notes

- When a server breaks down in Hadoop, data is still calculated and presented to user. Hadoop is suitable for reading continuously updating feeds of unstructured data and not managing transactions like SQL, which follows the two-phase commit (notify user if a server breaks down and tally might not add up).
- Because query is mapping and consolidation program, we can be creative with program. Java based query increases complexity of talking to Hadoop. We use packaged resource distribution like Hive to use standard SQL to access Hadoop.

5. This flexibility is the reason there’s so many practices and deployment type. But the tools for data management and analysis is beginning to write map reduce programs and pre-packaged schemas on lead to easier use Hadoop (code-less access to Hadoop).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTg3ODg0MTM4N119
-->