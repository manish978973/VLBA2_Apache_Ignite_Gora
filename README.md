### MAP REDUCE AND IoT DATABASES/IN_MEMORY COMPUTING POWERED BY APACHE IGNITE

Apache Ignite is a memory centric distributed database, caching, and processing platform that is durable strongly consistent and highly available with powerful SQL, key-value and processing APIs.

<Image src="Images/ApacheIntro.png" class="center" style="width:50%">
  
  
 ## SETTING UP THE JAVA and LINUX ENVIRONMENT 

This project was developed using IntelliJ IDEA integrated environment and in Ubuntu.Follow the [link ](https://www.jetbrains.com/help/idea/installation-guide.html) to set up the Java IDE.


## IGNITE-GETTING STARTED AND INSTALLING

* Download the Ignite Binary distribution as a ZIP archive from [link ](https://ignite.apache.org/) 
* Unzip the ZIP archive into the installation folder in your system.
* Set IGNITE_HOME environment variable/PATH to point to the installation folder and make sure there is no trailing in the path.
* To start a Ignite cluster node with default configuration, open the command shell and assuming you are in IGNITE_HOME, just type

`$ bin/ignite.sh`

* By default ignite.sh starts a node with the default configuration which is config/default-config.xml

* To pass a custom configuration file, pass the file as a parameter to **ignite.sh/bat** as follows :

`$ bin/ignite.sh customconfig.xml`

## HOOKING UP TO MAVEN

* Ignite requires only one **ignite-core** mandatory dependency.
* Usually, you will also need to add **ignite-spring** for spring-based XML configuration and **ignite-indexing** for SQL querying.
* Replace ${ignite-version} with the actual Ignite version.


### MEMORY CENTRIC STORAGE IN IGNITE

* In-memory processing coupled together with the disk durability and strong consistency
* Functioning as a memory centric system with native persistence switched on.
* By default persistence is turned off and Ignite functions as a In-Memory database
* Ignite provides strong ACID durability guarantee to the data.

<Image src="Images/ignitemem1.png" class="center" style="width:50%"> <Image src="Images/Ignitemem2.png" class="center" style="width:50%">

#### FEATURES OF IGNITE MEMORY CENTRIC STORAGE

##### <ins>In Memory Mode</ins>

* In-Memory - The whole dataset is stored in memory and processed. Backup copies are taken care to handle node failure.RAM is always treated as the first memory tier.
* Multiple API support as a part of Data processing, streaming and Tool integration.

##### <ins>Persistance Mode</ins>

* Data Resiliency – survive node crash as it sores data on disk
* Instantenous cluster restarts
* Superset of data stored in persistent disk and retrieved to main memory during processing hence increasing the performance.


#### INTEGRATION OF IGNITE WITH 3rd PARTY DATABASES AND VISUALIZATION TOOLS

* Apache Ignite can be used to accelerate existing applications running with legacy database management systems.
* Ignite can be employed as a In-memory caching layer over the existing persistent database like RDBMS ,Apache Cassandra and Mongo DB.
* Ignite provides APIs like CacheLoader and CacheWriter to connect to underlying SQL and NOSQL databases.

<Image src="Images/hbase.png" class="center" style="width:50%"><Image src="Images/cassandra.png" class="center" style="width:50%"><Image src="Images/sqlser.jpg" class="center" style="width:50%"><Image src="Images/zep.jpg" class="center" style="width:50%">
  
  

### DISTRIBUTED SQL IN IGNITE

* SQL  ACID Transactions
* Automatic Deadlock management when multiple transactions run.
* SQL and In-Memory Mode -- Apache Ignite can function in a pure in-memory mode in which all data and indexes are stored entirely in RAM. 
* SQL and Native Persistence -- In this mode, Ignite  serves as the primary storage that can survive cluster failures and restarts. On cluster restart, Ignite reads data and indexes from disk eliminating the need for memory warm-up. 
* Apache Ignite JDBC and ODBC drivers is used to connect to the cluster and process data stored there from a SQL tool like Dbeaver.
* The data in Ignite Cluster can be connected to 3rd party Visualization tools like **Zeppelin** and **Tableau** for further data analysis.


### DISTRIBUTED KEY_VALUE IN IGNITE

* The in-memory data grid component in Ignite is a fully transactional distributed key-value store that can scale upto 100s of servers in the cluster.
* Ignite portrays as a partitioned hash map with every cluster node owning a portion of the overall data set.
* Ignite key-value APIs support.
* In-Memory Key Value Store.
* Basic Cache operations.
* Pluggable Persistance (Native Disk or 3rd party database)


### COLLOCATED PROCESSING IN IGNITE

* Collocated processing is an add on feature over conventional Client-Server approach.
* Computations are carried over the server side rather than client side bringing down the latency and processing time.
* Advanced SQL queries and JOINS have been successful with this approach.

<Image src="Images/col.png" class="center" style="width:50%">
  
 ## FUNCTIONALITIES AND VIVID SERVICES WITH APACHE IGNITE
 
 <Image src="Images/igfea.png" class="center" style="width:50%">
  
  
  ### CLUSTERING IN IGNITE
  
* Ignite is an customizable horizontally scalable distributed system that endorses adding and removing cluster nodes on demand.
* Ignite cluster can be started with different configuration files . It is based on the configuration file that persistence is enabled or disabled.
* Each ignite node = Each JAVA Virtual Machine
* Customising Ignite nodes - Ignite has an optional notion of client and server nodes. Server nodes participate in caching, compute execution, stream processing, etc., while the native client nodes provide the ability to connect to the servers remotely. By default the ignite node starts as server unless specified.
* While creating a cache Ignite make sure that it deploys a distributed cache on all server nodes.
* Ignite nodes can automatically discover each other.(TCP/IP and Zookeeper Discovery) This helps to scale the cluster when needed, without having to restart the whole cluster.
* Ignite provides various Cluster APIs :

     `IgniteCluster which is an API Interface that’s used to start and stop Cluster.`
     
* Cluster groups can also  be customised to make it Remote, Cache , Client/Server.



 ### DATAGRID IN IGNITE

* Ignite data grid is an in-memory distributed key-value store with every cluster node owning a portion of the processing data.
* A plugging hashing algorithm is employed which makes a client to discover the appropriate node with the suitable key unlike the mapping server tagging.
* As long as cluster is alive Ignite will guarantee that the data between different cluster nodes will always remain consistent regardless 
* Ignite APIs for Data grid :
   `IgniteCache  -- which is employed to initialize a cache in newly deployed node.`
   `DynamicCache – which detects newly joined nodes and binds them.`
   
   ### STREAMING IN APACHE IGNITE
   
   * Ignite data loading and streaming capabilities allow ingesting large finite volumes of data as well as persistent/streaming data sources into the ignite cluster.
   * IGNITE APIs for Data Streaming :  `Data Streamer API-- built to inject large amounts of continuous streams of data into Ignite stream caches. It allows overwriting of data.`
   
   #### <ins>INTEGRATION WITH STREAMING TECHNOLOGIES</ins>
   
   * Kafka streamer , mqtt streamer , camel streamer , twitter streamer
   * MQTT Streamer – Feeds key-value pairs into an IgniteData Streamer instance using Eclipse Paho as an MQTT client.
   *  The Eclipse Paho project provides open-source client implementations of MQTT and MQTT-SN messaging protocols aimed at new, existing, and emerging applications for the Internet of Things (IoT).
   * This streamer supports subscribing to single or multiple topics at once.
   
   
     ### COMPUTER GRID IN APACHE IGNITE
     
* Ignite allows distributed  computations to be performed in parallel fashion to gain high performance, low latency and linear scalability.
* With Ignite computer grid APIs data can be processed in multiple nodes in the cluster.
* IgniteCompute is an API that can be employed to establish parallel processing of data.


     ### SERVICE GRID IN APACHE IGNITE

* The number of instances deployed in each cluster node can be controlled hence ensuring proper deployment and fault tolerance of all the services.
* Continuous availability and deployment of services regardless of topology crashes.
* Cluster Singleton - Ignite will guarantee that there is always one instance of the service in the cluster. In case the cluster node on which the service was deployed crashes or stops, Ignite will automatically redeploy it on another node. 
* Node Singleton - Ignite will guarantee that there is always one instance of the service running on each node. Whenever new nodes are started within the cluster group, Ignite will automatically deploy one instance of the service on every new node

## HADOOP ACCLERATION IN APACHE IGNITE

* Apache Ignite Hadoop Accelerator map-reduce engine processes Hadoop jobs within Ignite cluster. Several prerequisites must be satisfied. force all Hadoop jobs to pick Ignite jobs tracker by default. 
* MapReduce performs much better than Hadoop due to push-based resource allocation as well as in-process collocation of computations with data.

 <Image src="Images/apahad.png" class="center" style="width:50%">

### IGNITE SUPPORTED PLATFORMS

Apache ignite also provides unified API which supports C++,.NET,PHP,JAVA/Scala and Node.js protocols for the application layer.

### DEPLOYMENT OF APACHE IGNITE 

* Local System
* AWS Deployment
* Docker deployment
* Mesos and Yarn deployment
* MS Azure



 ## PERSISTENCE DIAGRAM OF APACHE IGNITE  
 
 * Applications that rely on 3rd party database and implementing Ignite just as caching medium.

 <Image src="Images/igdep1.png" class="center" height="150" width="600">

* Applications that  rely in Ignite for caching and Ignite persistence.

   <Image src="Images/igdep2.png" class="center" height="150" width="600">
  
  
   ## USECASES IMPLEMENTED IN APACHE IGNITE  
  
  #### <ins>USECASE 1</ins>
  
  
* We have parsed a log file (Access.log) into Apache Ignite Cluster with local persistance mode enabled.
* The log files are of (**now showdown**) server at [site ](http://www.buldinle.com).The file was obtained from Apache Gora's official portal.
* Example logs contain 10,000 lines between dates 2009/3/10-2009/03/15
* The first fields in order are User's IP,ignored,ignored,Date and time,HTTP method,URL,HTTP method, HTTP status code,Number of bytes returned and User Agent.

  <Image src="Images/igus1.png" class="center" height="150" width="600">
  
  The **PersistanceFlat.java** in src/main/java has the implementation to load the data stored in Access.log to the the local persistence database via Apache Ignite.The Apache Ignite cluster has been started with persistence mode enabled configuration file. This can be modified to switch back to In-memory mode from local persistence mode.Once the data is loaded we perform a basic query to fetch the data stored in the database. Also the query can be run from the external SQL tool DBeaver that has been linked to Apache Ignite cluster via JDBC driver. 
  
  

#### INTEGRATION OF APACHE IGNITE WITH EXTERNAL SQL TOOL - DBeaver

* Apache Ignite JDBC and ODBC drivers make it possible to connect to the cluster and process data stored there from a SQL tool of a choice.
* As an installation example we will use DBeaver, which is a is free and open source universal database tool for developers and database administrators. It supports all popular databases including Apache Ignite
* [Download ](https://dbeaver.jkiss.org/download/) and install DBeaver for an operating system of your choice and download the latest Apache Ignite version.

* Once DBeaver is installed, launch it and select the Database->Driver Manager menu item to configure the Apache Ignite JDBC driver. 
* Use Apache Ignite as a database/driver name and click on the New button
* Fill out the required settings on the next screen, as follows:

**Driver Name** - a custom name, set it to Apache Ignite for simplicity.
**Class Name** - set org.apache.ignite.IgniteJdbcThinDriver as a value.
**URL Template** - that's Ignite's JDBC connection string, jdbc:ignite:thin://127.0.0.1/ should be used a part of this getting started guide.
**Default Port** - port 10800 is used by Ignite's JDBC driver by default.
**Libraries tab** - click on Add file button and locate {apache-ignite-version}/libs/ignite-core-{version}.jar file that includes the Ignite's JDBC driver.

* Click on the OK button to complete the setup and close the Driver Manager dialog after that. You will see Apache Ignite among the drivers' list
* The next step is to start an Apache Ignite cluster and connect to it with DBeaver.
* To start a Ignite cluster node with default configuration, open the command shell and assuming you are in IGNITE_HOME, just type

`$ bin/ignite.sh`

* The script starts an Apache Ignite node. You can start as many nodes as you want using the same script.
* Switch back to DBeaver and select the Database->New Connection menu item. Look up Apache Ignite in the list and click on Next > button
* Ensure that the JDBC URL setting points to the previously set up jdbc:ignite:thin://127.0.0.1/ connection string and push the Test Connection ... button to validate the connectivity between DBeaver and the Apache Ignite cluster running locally
* If the test passes click on Next > on this and the following Network screen:
* Validate the settings on the final screen clicking on the Finish button at the en
* Apache Ignite will appear in Database Navigator tab
* Now click on the right mouse button to see a special menu and open SQL Editor so as to execute all SQL queries.


 #### <ins>USECASE 2</ins>
 
 * A  Hadooop map-reduce program with Ignite Hadoop accelerator to calculate the number of daily pageviews for each URL in the site from the log file is to be performed.
* The job will be performed in Ignite’s in-memory node.

 <Image src="Images/ighad.png" class="center" style="width:50%">


 
 
  









