5 Vs: volume, velocity, variety, veracity, and value.


When I say volume, I mean the amount of data that a solution must handle. 
The solution must do it efficiently and be able to distribute the load 
across enough servers to handle the next V: velocity.

The third V is variety—ingesting data of many different types from many
 different sources can mean many different challenges to data analysis. 
Smart companies build solutions to work with structured, semistructured,
 and completely unstructured data types

The fourth V is veracity, which refers to the trustworthiness of your data. 
Have you ever heard the saying, “My word is my bond”? It’s supposed to 
instill trust, to let you know that the person saying it is honorable and 
will do what they say they will. That’s veracity. To have trustworthy data,
 you have to know the provenance of your data.

Sure, provenance means that you know the chain of custody for that data. 
That you can say with certainty that the data has not be altered falsely. 
Collecting data is easy—making sure it’s accurate and consistent? That's 
the hard part—that’s veracity.

And the fifth V is value—which is the bottom line, really. The whole 
point of this effort is getting value from data. That includes creating 
reports and dashboards that inform critical business decisions. It also 
includes highlighting areas for improving the business. And it includes 
making it easier to find and communicate critical details about business 
operations.

So now what we’ve got is Amazon S3 that can host a data lake and Amazon
 Redshift that can host a data warehouse, but what if I need to query across both spaces?
Oh, I think I have a solution for that. Introducing Amazon Redshift Spectrum

extract, transform, and load (ETL) operations.

 Amazon EMR is a managed Hadoop framework. Remember that we talked earlier 
about the challenge of ingesting huge volumes of data quickly and rapidly 
producing insights? Well, this is what Amazon EMR does. Hadoop is an 
open-source framework that has been around for a long time and is well 
established in the data processing world.

A subset of data from a data warehouse is called a data mart.


When storing individual objects or files, we recommend Amazon S3.
When storing massive volumes of data, both semistructured and unstructured, 
we recommend building a data lake on Amazon S3. When storing massive amounts 
of structured data for complex analysis, we recommend storing your data in Amazon Redshift.


Amazon EMR has the ability to implement two different file systems: HDFS or the Elastic MapReduce File System (EMRFS). 


Generally speaking, there are two types of processing: batch processing and stream processing. 

 Batch processing comes in two forms: scheduled and periodic.

Stream processing also comes in two forms: real time and near-real time

 In stream processing, you use multiple services. One service to ingest the constant stream of data, 
one service to process and analyze the stream and another service to load the data into an analytical data store if required.



In AWS, we have a number of services for this purpose, including Amazon Kinesis Data Firehose 
and Amazon Kinesis Data Streams,which are used to ingest data streams and load the data stream
 into analytical data stores. Amazon Kinesis Data Analytics is used to process and analyze
 the data stream. Amazon Kinesis Data Analytics allows you to choose to query a rolling time
 window of data, say the last two minutes. The analysis is limited to only those records 
collected within that window of time. Because of this limitation, analytics on streaming data
 are often simple aggregates. The result of the analysis is made available to be viewed in a
 dashboard and/or be stored within an analytical data store. The latency in a stream processing 
system is seconds to milliseconds. Screaming fast! 

data acceleration, which means the rate at which large collections of data can be ingested, processed, 
and analyzed. Data acceleration is not constant. It comes in bursts. Take Twitter as an example. Hashtags
 can become hugely popular and appear hundreds of times in just seconds, or slow down to one tag an hour. 

Batch processing: Processes massive amounts of data at once. This requires a system that can collect and hold this data until the processing system can work through it all.

Periodic processing: Processes irregular unpredictable workloads. The impossibility of predicting these workloads puts tremendous strain on big data systems.

Near real-time processing: Processes small bursts of data that must be collected and processed within minutes of collection.

Real-time processing: Processes tiny bursts of data continuously. This data must be presented to the analytics phase within moments of collection.

Next, let’s use a processing service called AWS Lambda. Using AWS Lambda, we will create a program to run once every four hours to 
grab any new data from the Amazon S3 bucket and send it to Amazon EMR for processing. This program creates the batches.



This is where AWS Glue come in. AWS Glue is a fully managed ETL service that categorizes, cleans, enriches, 
and moves your data reliably between various data stores. AWS Glue simplifies and automates difficult and 
time-consuming data discovery, conversion, mapping, and job-scheduling tasks. In other words, it simplifies
 data processing.
 
 
 AWS Lambda is a serverless compute service that can be used to trigger processing operations in a batch processing system.
 
 Amazon EMR is a managed service for executing highly complex, massive batch workloads. This service also allows highly complex analytic operations.
 
 Amazon Kinesis Data Firehose, Amazon Kinesis Data Streams, and Amazon Kinesis Data Analytics. A fourth capability of Kinesis is 
 Amazon Kinesis Video Streams. This service makes it easy to securely stream video from connected devices to AWS for analytics, 
 machine learning (ML), and other processing.
 
 Amazon Athena is an interactive query service that makes it easy to analyze data in Amazon S3 using the standard structured query language 
 (SQL). Athena is serverless, so there is no infrastructure to manage, and you pay only for data scanned by the queries you run
 
 Amazon QuickSight is a fast, cloud-powered business intelligence service that makes it easy for you to deliver insights to everyone in your organization
 
 
 
 Amazon Kinesis Data Firehose is the easiest way to capture, transform, and load data streams into AWS data stores for near real-time analytics 
 with existing business intelligence tools. 
 

Amazon Kinesis Data Streams enables you to build custom, real-time applications that process data streams using popular stream processing frameworks. 

Amazon Kinesis Video Streams makes it easy to securely stream video from connected devices to AWS for analytics, machine learning (ML), and other processing. 
Amazon  athena  is an interactive query service that makes it easy to analyze data in Amazon S3 using standard SQL.


Amazon Kinesis Data Analytics is the easiest way to process data streams in real time with SQL or Java without having to learn new programming languages or processing frameworks.

relational - online transaction processing, or OLTP, and online analytical processing, or OLAP. 
The solution is to have one database optimized for write operations, OLTP, and one optimized for read operations, OLAP.

or OLTP or OLAP databases using row-based indexing, we have Amazon Relational Database Service, also called Amazon RDS.


For OLAP databases using columnar indexing, we have Amazon Redshift,


Amazon DynamoDB is the service used for NoSQL data storage. DynamoDB is a key-value and document store database that delivers 
single-digit millisecond performance at any scale. It's a fully managed, multi-Region, multi-master database with built-in 
security, backup and restore, and in-memory caching for internet-scale applications.

The AWS graph database service is called Amazon Neptune. 

Databases are always optimized to achieve a specific goal. In relational databases, the goal is optimized storage. NoSQL
 databases place the emphasis on compute power, and NoSQL graph databases are optimized for relationships.

Relational databases are very good at growing by adding more resources. This is known as vertical scaling. NoSQL
 databases are good at being distributed across multiple servers or instances. This is known as horizontal scaling. 
NoSQL Graph databases are good at both types of scaling.

 Relational databases are commonly used as the backbone of OLTP business systems and OLAP data warehouses. NoSQL
 and graph databases are both commonly used for OLTP web and mobile applications.

Amazon DynamoDB is a key-value and document database that delivers single-digit millisecond performance at any scale.
 It's a fully managed, multiregion, multimaster database with built-in security, backup and restore, and in-memory
 caching for internet-scale applications. 

Amazon Neptune is a fast, reliable, fully managed graph database service that makes it easy to build and run 
applications that work with highly connected data sets.

Relational integrity ensures that both members of a relationship remain consistent.
Entity integrity ensures that values within a field remain consistent.

An information schema is a database of metadata containing information on all database objects.

A logical schema lists the constraints, relationships, and properties of tables and views in a database.

Atomicity ensures that all the statements either succeed together or fail together. No one statement can succeed without the others.



The C stands for consistency. For a transaction to complete successfully, all of the statements within it must meet all 
constraints set in the database. If any single statement violates these checks, the whole transaction is rolled back, and 
the database is returned to its previous state. This also ensures that data updates are not made available until all replicates
 have been updated as well.

The I stands for isolation. Isolation ensures that one transaction cannot interfere with another concurrent transaction. 
Databases are busy places. Isolation ensures that when multiple transactions request the same data, the data isn’t 
corrupted as a result.

The D stands for durability. Data durability is all about making sure your changes actually stick. Once a transaction
 is complete, durability ensures that the result of the transaction is permanent even if there’s a system failure.
 This means that all completed transactions that result in a new record or update to an existing record are written
 to storage and don’t remain in memory only.


BASE is an acronym for Basically Available Soft state Eventually 

Amazon EMR is a more hands-on approach to creating your data pipeline. This service provides a robust data 
collection and processing platform. Using this service requires you to have strong technical knowledge and 
know-how on your team. The upside of this is that you can create a more customized pipeline to fit your 
business needs. Additionally, your infrastructure costs may be lower than running the same workload on AWS Glue.

AWS Glue is a serverless, managed ETL tool that provides a much more streamlined experience than Amazon EMR. 
This makes the service great for simple ETL tasks, but you will not have as much flexibility as with Amazon 
EMR. You can also use AWS Glue as a metastore for your final transformed data by using the AWS Glue Data Catalog. 
This catalog is a drop-in replacement for a Hive metastore.

Data analytics comes in two classifications, information analytics, and operational analytics.

Amazon QuickSight is a fast, easy-to-use, cloud-powered business analytics service that makes it easy for all 
employees within an organization to build visualizations, perform one-time analyses, and quickly get business 
insights from their data, any time, on any device.


