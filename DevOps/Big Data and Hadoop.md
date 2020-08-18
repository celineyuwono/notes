## Big Data and Hadoop

### Source URL: [https://www.youtube.com/watch?v=iANBytZ26MI](https://www.youtube.com/watch?v=iANBytZ26MI)

1. **Parallel processing:** Using multiple processors for high volume of data with different formats/diff kinds of data (structured, semi-structured, unstructured). For example, even in a tweet, it is a mix of data so using a single processor is impossible, too time consuming. In other words, parallel processing = distributed storage and multiple processors. 

Screenshot

2.  **Big Data:** Massive amount of data that cannot be stored, processed, analyzed using traditional ways. Big Data is used when data has high volume, requires high velocity/speed to get, has huge variety that requires high processing, must be reduced to a certain value/pre-processed, veracity/data has uncertainty, meaning high processing (ex. Twitter data).
3. Big Data challenges -> solutions solved by Hadoop:
	- Single central storage -> Distributed storage.
	- Serial processing -> Parallel processing.
	- Lack of ability to process unstructured data (or mix of data) -> ability to do so.
 **Hadoop:** Framework that manages big data storage in a distributed way and processes it parallelly. 

### Hadoop Components
1. **Hadoop storage unit (Hadoop HDFS):** Specially designed for storing huge datasets in commodity hardware.
	- **NameNode (Master):** Only 1 and backup. Enterprise computer. Maintains and manages the DataNode and stores the metadata.
	- **DataNode (Slaves):** Multiple. Usually at least 5~10. Commodity computer. DataNodes stores the actual data, does reading, writing, and processing. Performs replication as well.
	- Commodity computer is way cheaper than enterprise computer.

<![if !supportLists]> iv. <![endif]>NameNode and DataNode connected by HeartBeat: Signal that DataNode continuously sends to NameNode, shows status of DataNode.

<![if !supportLists]> v. <![endif]>Data is stored in HDFS in distributed manner. Ex. 30TB is loaded into NameNode, then NameNode divided data to 128MB each. Data is then distributed among DataNodes (Data security: randomly, and replicated default 3x among DataNodes). Fault tolerant: If one commodity machines go down, we can easily set up another one.

<![if !supportLists]>b. <![endif]>Processing unit (Hadoop MapReduce): Programming technique where huge data is processed in a parallel and distributed function. <![if !vml]>![A screenshot of a cell phone

Description automatically generated](file:////Users/ts-celine.yuwono/Library/Group%20Containers/UBF8T346G9.Office/TemporaryItems/msohtmlclip/clip_image002.png)<![endif]>

<![if !supportLists]> i. <![endif]>Big Data -> Processor (Hadoop MapReduce) -> Output

<![if !supportLists]> ii. <![endif]>In MapReduce, processing is done at the slave nodes and the final result is sent to the master node. NameNode send piece of code to DataNode to process the data using code.

<![if !supportLists]>c. <![endif]>Resource Management Unit for Hadoop 2 and above. (Hadoop Yarn) <![if !vml]>![A screenshot of a cell phone

Description automatically generated](file:////Users/ts-celine.yuwono/Library/Group%20Containers/UBF8T346G9.Office/TemporaryItems/msohtmlclip/clip_image003.png)<![endif]>

<![if !supportLists]> i. <![endif]>YARN – Yet another resource negotiator.

<![if !supportLists]> ii. <![endif]>Acts like an OS to Hadoop 2 but controlling across computers (like Apple OS or Linux). Manages cluster resources and job scheduling.

<![if !supportLists]> iii. <![endif]>Process: Client submits the job request -> Resource manager allocates and manages resources (sits on top of everything) -> Node Manager manages the nodes and monitors resource usage (in the node of each computer).

<![if !supportLists]> iv. <![endif]>Inside Node Manager: Container is a collection of physical resources such as RAM, CPU. App Master requests container from the NodeManager (Ex. I need CPU for this process).

<![if !supportLists]>5. <![endif]>What is MapReduce?

<![if !supportLists]>a. <![endif]>Input is split into chunks of data (by email, by document, by twitter feed, by DB row etc.) and mapped (process where you only need chunk of data that doesn’t require any other data, ex. Organizing data). Result will be attached to key, becoming key and value after mapping. Shuffle and sort using the key, then reduce.

<![if !supportLists]>6. <![endif]>Uses of Hadoop

<![if !supportLists]>a. <![endif]>Storing massive amount of unstructured data.

<![if !supportLists]>b. <![endif]>Processing unstructured data.

<![if !supportLists]>c. <![endif]>Analyzing is time efficient and easy.

<![if !supportLists]>d. <![endif]>Detecting information through monitoring and generate many information from processing.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTk0MDI5MDQ3NV19
-->