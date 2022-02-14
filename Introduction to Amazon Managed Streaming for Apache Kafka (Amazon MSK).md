# Introduction

* Amazon MSK is a fully managed service that makes it easy for you to build and run applications that use Apache Kafka to process streaming data. Apache Kafka is an open-source platform for building real-time streaming data pipelines and applications. 

* With Amazon MSK, you can use native Apache Kafka APIs to populate data lakes, stream changes to and from databases, and power machine learning and analytics applications.

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/f7qpu4gt84ewvwvh7qd6.png) 

> **Big Data Analytics Options on AWS** is a Series containing different articles that provides a basic introduction to different Big Data Analytics Options on AWS. Each article covers the detailed guide on how each service is used for collecting, processing, storing, and analyzing big data.

* Apache Kafka clusters are challenging to set up, scale, and manage in production. When you run Apache Kafka on your own, you need to provision servers, configure Apache Kafka manually, replace servers when they fail, orchestrate server patches and upgrades, architect the cluster for high availability, ensure data is durably stored and secured, set up monitoring and alarms, and carefully plan scaling events to support load changes.

* Amazon MSK makes it easy for you to build and run production applications on Apache Kafka without needing Apache Kafka infrastructure management expertise.

* With a few clicks in the Amazon MSK console (sign-in required), you can create a fully managed Apache Kafka cluster that follows Apache Kafka’s deployment best practices, or you can create your own cluster using your own custom configuration. 

* After you create your desired configuration, Amazon MSK automatically provisions, configures, and manages the operations of your Apache Kafka cluster and Apache ZooKeeper nodes.

* An Amazon MSK cluster is the primary Amazon MSK resource that you can create in your account.

* Following are the primary components that work together in MSK:

 * **Broker nodes** — When creating an Amazon MSK cluster, you specify how many broker nodes you want Amazon MSK to create in each Availability Zone. Each Availability Zone has its own virtual private cloud (VPC) subnet.

 * **ZooKeeper nodes** — Amazon MSK also creates the Apache ZooKeeper nodes for you. Apache ZooKeeper is an open-source server that enables highly reliable distributed coordination.

 * **Producers, consumers, and topic creators** — Amazon MSK enables you to use Apache Kafka data-plane operations to create topics and to produce and consume data.

 * **Cluster operations** — You can use the AWS Management Console, the AWS Command Line Interface (AWS CLI), or the APIs in the SDK to perform control-plane operations. For example, you can create or delete an Amazon MSK cluster, list all the clusters in an account, view the properties of a cluster, and update the number and type of brokers in a cluster.

* Amazon MSK detects and automatically recovers from the most common failure scenarios for clusters, so that your producer and consumer applications can continue their write and read operations with minimal impact. 

* When Amazon MSK detects a broker failure, it mitigates the failure or replaces the unhealthy or unreachable broker with a new one. In addition, where possible, it reuses the storage from the older broker to reduce the data that Apache Kafka needs to replicate. 

* Your availability impact is limited to the time required for Amazon MSK to complete the detection and recovery. After a recovery, your producer and consumer apps can continue to communicate with the same broker IP addresses that they used before the failure.

# Ideal usage patterns

* The AWS Streaming Data Solution for Amazon MSK enables you to capture, store, process, and deliver real-time streaming data. This service helps you address real-time streaming use cases; for example:

 * Capture high volume application log files

 * Analyze website clickstreams

 * Process database event streams

 * Track financial transactions

 * Aggregate social media feeds

 * Collect IT log files

 * Continuously deliver to a data lake

# Cost model

* Amazon MSK has a simple “pay only for what you use” model. There are no minimum fees or upfront commitments. There are charges for the time your broker instances run, the storage used monthly, and standard data transfer fees for data in and out of the cluster. 

* Apache Kafka broker instance usage is billed on an hourly basis (billed at one second resolution), with varying fees depending on the size of the Apache Kafka broker instance and active brokers in your Amazon MSK clusters. 

* Amazon MSK charges for the amount of storage you provision in the cluster. This is calculated by adding up the GB per broker each hour and dividing by the number of hours in the month, resulting in a value in "GB-Month."

* There are no additional charges for data transfer between brokers or between Apache ZooKeeper nodes and brokers. Standard AWS data transfer charges are charged for data transferred in and out of Amazon MSK clusters. See Amazon MSK pricing for further details.

# Performance

* Amazon MSK allows you to choose the right type and number of brokers for yourcluster. You can size your cluster based on your ingestion rate, hours of retention and data output rates. 

* The number of partitions per broker is affected by use case and configuration. To determine the right number of brokers for your MSK cluster and understand costs, see the MSK Sizing and Pricing spreadsheet (file download). For more information about the different broker types, see Broker types.

# Durability and availability

* Use the following recommendations so that your MSK cluster can be highly available during an update (such as when you're updating the broker type or Apache Kafka version, for example) or when Amazon MSK is replacing a broker.

* Ensure that the replication factor (RF) is at least two for two-AZ clusters and at least three for three-AZ clusters. An RF of one can lead to offline partitions during a rolling update.

* Set minimum in-sync replicas (minISR) to at most RF-1. A minISR that is equal to the RF can prevent producing to the cluster during a rolling update. A minISR of two allows three-way replicated topics to be available when one replica is offline.

* Ensure client connection strings include multiple brokers. Having multiple brokers in a client’s connection string allows for failover when a specific broker is offline for an update.

# Scalability and elasticity

* You can increase the capacity of the cluster at any time according to your business or operational needs. You can use Amazon MSK operation to increase the number of brokers in your MSK cluster. To expand a cluster, make sure that it is in the ACTIVE state.

* You can also increase storage per broker. You can increase the amount of EBS storage per broker, but you can't decrease the storage. Storage volumes remain available during this scaling-up operation. You can use:

 * **Automatic scaling** — You can configure Amazon Managed Streaming for Apache Kafka to automatically expand your cluster's storage in response to increased usage using Application Auto Scaling policies. Your automatic scaling policy sets the target disk utilization and the maximum scaling capacity.

 * **Manual scaling** — To increase storage, wait for the cluster to be in the ACTIVE state. Storage scaling has a cooldown period of at least six hours between events. Even though the operation makes additional storage available right away, the service performs optimizations on your cluster that can take up to 24 hours or more. The duration of these optimizations is proportional to your storage size.

# Interfaces

Amazon MSK has deep AWS service integrations with Amazon EMR, AWS Lambda, Amazon Kinesis Data Analytics, and AWS Glue Streaming ETL. It also works with Kafka Connect, Mirror Maker, Kafka Streams, and a number of 3rd party frameworks like Apache Spark, Apache Storm, and so on. The producer side APIs add messages to the cluster for a topic. The consumer side APIs get messages for a topic as a stream of messages.

# Anti-patterns
Amazon MSK has the following anti-patterns:

 * **Ad hoc queries** — MSK is a stream of unbounded data. It is not used for ad hoc queries.

 * **Long-term data storage and analytics** — MSK is not suited for long-term data storage.

---

Hope this guide gives you an Introduction to Amazon Managed Streaming for Apache Kafka (Amazon MSK).

Let me know your thoughts in the comment section 👇
And if you haven't yet, make sure to follow me on below handles:

👋 **connect with me on [LinkedIn](https://www.linkedin.com/in/adit-modi-2a4362191/)**
🤓 **connect with me on [Twitter](https://twitter.com/adi_12_modi)**
🐱‍💻 **follow me on [github](https://github.com/AditModi)**
✍️ **Do Checkout [my blogs](https://aditmodi.hashnode.dev)** 

Like, share and follow me 🚀 for more content.

{% user aditmodi %}

---

[Reference Notes](https://docs.aws.amazon.com/whitepapers/latest/big-data-analytics-options/amazon-msk.html)