# Introduction

* **Amazon Kinesis** is a platform for streaming data on AWS that makes it easy to load and analyze streaming data. Amazon Kinesis also enables you to build custom streaming data applications for specialized needs. 

* With Kinesis, you can ingest real-time data such as application logs, website clickstreams, Internet of Things (IoT) telemetry data, and more into your databases, data lakes, and data warehouses, or build your own real-time applications using this data. 

* Amazon Kinesis enables you to process and analyze data as it arrives and respond in real-time instead of having to wait until all your data is collected before the processing can begin.

* Currently there are four pieces of the Kinesis platform that can be utilized based on your use case:

 * **Amazon Kinesis Data Streams** enables you to build custom applications that process or analyze streaming data.

 * **Amazon Kinesis Video Streams** enables you to build custom applications that process or analyze streaming video.

 * **Amazon Kinesis Data Firehose** enables you to deliver real-time streaming data to AWS destinations such as such as Amazon S3, Amazon Redshift, OpenSearch Service, and Splunk.

 * **Amazon Kinesis Data Analytics** enables you to process and analyze streaming data with standard SQL or with Java (managed Apache Flink).

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/687ydk73s4r9gv8vkpjt.png) 

> **Big Data Analytics Options on AWS** is a Series containing different articles that provides a basic introduction to different Big Data Analytics Options on AWS. Each article covers the detailed guide on how each service is used for collecting, processing, storing, and analyzing big data.


* Kinesis Data Streams and Kinesis Video Streams enable you to build custom applications that process or analyze streaming data in real time. 

* Kinesis Data Streams can continuously capture and store terabytes of data per hour from hundreds of thousands of sources, such as website clickstreams, financial transactions, social media feeds, IT logs, and location-tracking events. 

* Kinesis Video Streams can continuously capture video data from smartphones, security cameras, drones, satellites, dashcams, and other edge devices.

* With the Amazon Kinesis Client Library (KCL), you can build Amazon Kinesis applications and use streaming data to power real-time dashboards, generate alerts, and implement dynamic pricing and advertising. 

* You can also emit data from Kinesis Data Streams and Kinesis Video Streams to other AWS services such as Amazon S3, Amazon Redshift, Amazon EMR, and AWS Lambda.

* Provision the level of input and output required for your data stream, in blocks of one megabyte per second (MB/sec), using the AWS Management Console, API, or SDKs. 

* The size of your stream can be adjusted up or down at any time without restarting the stream and without any impact on the data sources pushing data to the stream. Within seconds, data put into a stream is available for analysis.

* With Amazon Kinesis Data Firehose, you don't need to write applications or manage resources. You configure your data producers to send data to Kinesis Data Firehose and it automatically delivers the data to the AWS destination or third party (Splunk) that you specified. 

* You can also configure Kinesis Data Firehose to transform your data before data delivery. It is a fully managed service that automatically scales to match the throughput of your data and requires no ongoing administration. 

* It can also batch, compress, and encrypt the data before loading it, minimizing the amount of storage used at the destination and increasing security.

* Amazon Kinesis Data Analytics is the easiest way to process and analyze real-time, streaming data. With Kinesis Data Analytics, you just use standard SQL or Java (Flink) to process your data streams, so you don’t have to learn any new programming languages.

* Simply point Kinesis Data Analytics at an incoming data stream, write your SQL queries, and specify where you want to load the results. Kinesis Data Analytics takes care of running your SQL queries continuously on data while it’s in transit and sending the results to the destinations.

* For complex data processing applications, Amazon Kinesis Data Analytics provides an option use open-source libraries such as Apache Flink, Apache Beam, AWS SDK, and AWS service integrations. It includes more than ten connectors from Apache Flink, and gives you the ability to build custom integrations. 

* It’s also compatible with the AWS Glue Schema Registry, a serverless feature of AWS Glue that enables you to validate and control the evolution of streaming data using registered Apache Avro schemas.

* You can use Apache Flink in Amazon Kinesis Data Analytics to build applications whose processed records affect the results exactly once, referred to as exactly once processing. 

* This means that even in the case of an application disruption, like internal service maintenance or user-initiated application update, the service will ensure that all data is processed and there is no duplicate data. 

* The service stores previous and in-progress computations, or state, in running application storage. This enables you to compare real-time and past results over any time period, and provides fast recovery during application disruptions.

* The subsequent sections focus primarily on **Amazon Kinesis Data Streams**.

## Ideal usage patterns

* Amazon Kinesis Data Steams is useful wherever there is a need to move data rapidly off producers (data sources) and continuously process it. 

* That processing can be to transform the data before emitting into another data store, drive real-time metrics and analytics, or derive and aggregate multiple streams into more complex streams, or downstream processing. 

* The following are typical scenarios for using Kinesis Data Streams for analytics:

**Real-time data analytics** – Kinesis Data Streams enables real-time data analytics on streaming data, such as analyzing website clickstream data and customer engagement analytics.

**Log and data feed intake and processing** – With Kinesis Data Streams, you can have producers push data directly into an Amazon Kinesis stream. For example, you can submit system and application logs to Kinesis Data Streams and access the stream for processing within seconds. This prevents the log data from being lost if the front-end or application server fails, and reduces local log storage on the source. Kinesis Data Streams provides accelerated data intake because you are not batching up the data on the servers before you submit it for intake.

**Real-time metrics and reporting** – You can use data ingested into Kinesis Data Streams for extracting metrics and generating KPIs to power reports and dashboards at real-time speeds. This enables data-processing application logic to work on data as it is streaming in continuously, rather than waiting for data batches to arrive.

## Cost model

* Amazon Kinesis Data Streams has simple pay-as-you-go pricing, with no upfront costs or minimum fees, and you pay only for the resources you consume. 

* An Amazon Kinesis stream is made up of one or more shards. Each shard gives you a capacity of five read transactions per second, up to a maximum total of 2 MB of data read per second. Each shard can support up to 1,000 write transactions per second, and up to a maximum total of 1 MB data written per second.

* The data capacity of your stream is a function of the number of shards that you specify for the stream. The total capacity of the stream is the sum of the capacity of each shard. There are two components to pricing:

* Primary pricing includes an hourly charge per shard and a charge for each one million PUT transactions.

* Pricing for optional components for extended retention and enhanced fan-out.

* For more information, see Amazon Kinesis Data Streams Pricing. Applications that run on Amazon EC2 and process Amazon Kinesis streams also incur standard Amazon EC2 costs.

## Performance

* Amazon Kinesis Data Streams enables you to choose the throughput capacity you require in terms of shards. With each shard in an Amazon Kinesis stream, you can capture up to 1 megabyte per second of data at 1,000 write transactions per second. 

* Your Amazon Kinesis applications can read data from each shard at up to 2 megabytes per second. You can provision as many shards as you need to get the throughput capacity you want; for example, a one gigabyte per second data stream would require 1024 shards.

* Additionally, there is a new feature. Enhanced fan-out enables developers to scale up the number of stream consumers (applications reading data from a stream in real-time) by offering each stream consumer their own read throughput. 

* Developers can register stream consumers to use enhanced fan-out and receive their own 2MB/sec pipe of read throughput per shard. This throughput automatically scales with the number of shards in a stream.

## Durability and availability

* Amazon Kinesis Data Streams synchronously replicates data across three Availability Zones in an AWS Region, providing high availability and data durability.

* Additionally, you can store a cursor in Amazon DynamoDB to durably track what has been read from an Amazon Kinesis stream. In the event that your application fails in the middle of reading data from the stream, you can restart your application and use the cursor to pick up from the exact spot where the failed application left off.

## Scalability and elasticity

* You can increase or decrease the capacity of the stream at any time according to your business or operational needs, without any interruption to ongoing stream processing. 

* By using API calls or development tools, you can automate scaling of your Amazon Kinesis Data Streams environment to meet demand and ensure you only pay for what you need.

## Interfaces

* There are two interfaces to Kinesis Data Streams:

 * **Input** which is used by data producers to put data into Kinesis Data Streams

 * **Output** to process and analyze data that comes in

* Producers can write data using the Amazon Kinesis PUT API, an AWS Software Development Kit (SDK) or toolkit abstraction, the Amazon Kinesis Producer Library (KPL), or the Amazon Kinesis Agent.

* For processing data that has already been put into an Amazon Kinesis stream, there are client libraries provided to build and operate real-time streaming data processing applications. The KCL acts as an intermediary between Amazon Kinesis Data Streams and your business applications which contain the specific processing logic. There is also integration to read from an Amazon Kinesis stream into Apache Spark Streaming running on Amazon EMR.

## Anti-patterns

* Amazon Kinesis Data Streams has the following anti-patterns:

 * **Small scale consistent throughput** – Even though Kinesis Data Streams works for streaming data at 200 KB per second or less, it is designed and optimized for larger data throughputs.

 * **Long-term data storage and analytics** – Kinesis Data Streams is not suited for long-term data storage. By default, data is retained for 24 hours, and you can extend the retention period by up to 365 days.

---

Hope this guide gives you an Introduction to Amazon Kinesis.

Let me know your thoughts in the comment section 👇
And if you haven't yet, make sure to follow me on below handles:

👋 **connect with me on [LinkedIn](https://www.linkedin.com/in/adit-modi-2a4362191/)**
🤓 **connect with me on [Twitter](https://twitter.com/adi_12_modi)**
🐱‍💻 **follow me on [github](https://github.com/AditModi)**
✍️ **Do Checkout [my blogs](https://aditmodi.hashnode.dev)** 

Like, share and follow me 🚀 for more content.

{% user aditmodi %}

---

[Reference Notes](https://docs.aws.amazon.com/whitepapers/latest/big-data-analytics-options/amazon-kinesis.html)