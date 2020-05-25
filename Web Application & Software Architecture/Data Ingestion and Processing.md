## Data Ingestion
  - Data Ingestion is a collective term for the process of collecting data streaming-in from several different sources and making it ready to be processed by the system.
  <img src="https://github.com/xidaniel/Full-Stack-Develop-Notes/blob/master/Web%20Application%20%26%20Software%20Architecture/images/Data%20Ingestion.jpeg" width=500>

## How to ingest data
  - Real-time
  - Batches
  - Stream Processing Engines for Real-Time Events:
    - Message queues like Kafka, Stream computation frameworks like Apache Storm, Apache Nifi, Apache Spark, Samza, Kinesis etc
  
## Data Pipelines
  - Data pipelines are the core component of a data processing infrastructure. They facilitate the efficient flow of data from one point to another & also enable the developers to apply filters on the data streaming-in in real-time.
  - Features:
    - These ensure smooth flow of data
    - Enables the business to apply filters and business logic on streaming data
    - Avert any bottlenecks & redundancy in the data flow
    - Facilitate parallel processing of data
    - Avoid data being corrupted
  - ETL (Extract Transform Load)
    - The ETL flow is the same as the data ingestion flow.
  
## Distributed Data Processing
  - Distributed data processing means diverging large amounts of data to several different nodes, running in a cluster, for parallel processing.
  - All the nodes execute the task allotted parallelly, working in conjunction with each other co-ordinated by a node-co-ordinator.
  - Tools:
    - MapReduce – Apache Hadoop
    - Apache Spark
    - Apache Storm
    - Apache Kafka
    - Hadoop is preferred for batch processing of data whereas Spark, Kafka & Storm are preferred for processing real-time streaming data.
   <img src="https://github.com/xidaniel/Full-Stack-Develop-Notes/blob/master/Web%20Application%20%26%20Software%20Architecture/images/Distributed%20Data%20Processing.jpeg" width=500>
   
## Data Processing Architecture
<img src="https://github.com/xidaniel/Full-Stack-Develop-Notes/blob/master/Web%20Application%20%26%20Software%20Architecture/images/Lambda%20Data%20Processing%20Architecture.jpeg" width=500>
<img src="https://github.com/xidaniel/Full-Stack-Develop-Notes/blob/master/Web%20Application%20%26%20Software%20Architecture/images/Kappa%20Data%20Processing%20Architecture.jpeg" width=500>
 
 - Kappa is preferred if the batch and the streaming analytics results are fairly identical in a system. Lambda is preferred if they are not.
    - Lambda Architecture
      - Lambda architecture makes the most of the two approaches.
      - The Batch Layer deals with the results acquired via batch processing the data. The Speed layer gets data from the real-time streaming data processing & the Serving layer combines the results obtained from both the Batch & the Speed layers.

    - Kappa Architecture
      - Kappa contains only two layers. Speed, which is the streaming processing layer, & the Serving which is the final layer. 
