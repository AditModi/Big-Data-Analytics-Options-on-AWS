# Introduction

* AWS offers the broadest and deepest set of machine learning services and supporting cloud infrastructure, putting machine learning in the hands of every developer, data scientist, and expert practitioner. 

* When you build an ML-based workload in AWS, you can choose from three different levels of ML services to balance speed-to-market with level of customization and ML skill level:

 * Artificial Intelligence (AI) services

 * ML services

 * ML frameworks and infrastructure

* The AI Services level provides fully managed services that enable you to quickly add ML capabilities to your workloads using API calls. 

* This gives you the ability to build powerful, intelligent applications with capabilities such as computer vision, speech, natural language, chatbots, predictions, and recommendations. 

* Services at this level are based on pre-trained or automatically trained machine learning and deep learning models, so you don’t need ML knowledge to use them.

* You can use:

 * **Amazon Translate** to translate or localize text content

 * **Amazon Polly** for text-to-speech conversion

 * **Amazon Lex** for building conversational chat bots

 * **Amazon Comprehend** to extract insights and relationships from unstructured data

 * **Amazon Forecast** to build accurate forecasting models

 * **Amazon Fraud Detector** to identify potentially fraudulent online activities,

 * **Amazon CodeGuru** to automate code reviews and to identify most expansive lines of code

 * **Amazon Textract** to extract text and data from documents automatically

 * **Amazon Rekognition** to add image and video analysis to your applications

 * **Amazon Kendra** to reimagines enterprise search for your websites and applications

 * **Amazon Personalize** for real-time personalized recommendations

 * **Amazon Transcribe** to add speech to text capabilities to your applications

* The ML Services level provides managed services and resources for machine learning to developers, data scientists, and researchers.

 * **Amazon SageMaker** enables developers and data scientists to quickly and easily build, train, and deploy ML models at any scale.

 * **Amazon SageMaker Ground Truth** helps you build highly accurate ML training datasets quickly.

 * **Amazon SageMaker Studio** is the first integrated development environment for machine learning to build, train, and deploy ML models at scale.

 * **Amazon SageMaker Autopilot** automatically builds, trains, and tunes the best ML models based on your data, while enabling you to maintain full control and visibility.

 * **Amazon SageMaker JumpStart** helps you quickly and easily get started with ML.

 * **Amazon SageMaker Data Wrangler** reduces the time it takes to aggregate and prepare data for ML from weeks to minutes.

 * **Amazon SageMaker Feature Store** is a fully managed, purpose-built repository to store, update, retrieve, and share ML features.

 * **Amazon SageMaker Clarify** provides ML developers with greater visibility into your training data and models so you can identify and limit bias and explain predictions.

 * **Amazon SageMaker Debugger** optimizes ML models with real-time monitoring of training metrics and system resources.

 * **Amazon SageMaker's distributed training libraries** automatically split large deep learning models and training datasets across AWS graphics processing unit (GPU) instances in a fraction of the time it takes to do manually.

 * **Amazon SageMaker Pipelines** is the first purpose-built, easy-to-use continuous integration and continuous delivery (CI/CD) service for ML.

 * **Amazon SageMaker Neo** enables developers to train ML models once, and then run them anywhere in the cloud or at the edge.

# Introduction

* Amazon EC2, with instances acting as AWS virtual machines, provides an ideal platform for operating your own self-managed big data analytics applications on AWS infrastructure. 

* Almost any software you can install on Linux or Windows virtualized environments can be run on Amazon EC2, and you can use the pay-as-you-go pricing model.

* AWS Graviton processors are custom built by AWS using 64-bit Arm Neoverse cores to deliver the best price performance for your cloud workloads running in Amazon EC2. 

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/e4cb455fcyp3iowjfbni.png)
 
> **Big Data Analytics Options on AWS** is a Series containing different articles that provides a basic introduction to different Big Data Analytics Options on AWS. Each article covers the detailed guide on how each service is used for collecting, processing, storing, and analyzing big data.

* Amazon EC2 provides the broadest and deepest portfolio of compute instances, including many that are powered by latest-generation Intel and AMD processors. AWS Graviton processors add even more choice to help customers optimize performance and cost for their workloads.

* What you don’t get are the application-level managed services that come with the other services mentioned in this whitepaper. There are many options for self-managed big data analytics:

 * A NoSQL offering, such as MongoDB

 * A data warehouse or columnar store like Vertica

 * A Hadoop cluster

 * An Apache Storm cluster

 * An Apache Kafka environment

* Any self-managed big data workload that runs on EC2 can also run on an AWS fully managed container orchestration service such as Amazon ECS, Amazon EKS, and AWS Fargate. Fargate is a serverless compute engine for containers that works with ECS and EKS.

# Ideal usage patterns

 * **Specialized environment** – When running a custom application, a variation of a standard Hadoop set or an application not covered by another AWS offering, Amazon EC2 provides the flexibility and scalability to meet your computing needs.

 * **Compliance requirements** – Certain compliance requirements may require you to run applications yourself on Amazon EC2 instead of using a managed service offering.

# Cost model

* Amazon EC2 has a variety of instance types in a number of instance families (standard, high CPU, high memory, high I/O, and so on), and different pricing options (On-Demand, Compute Savings plan, Reserved, and Spot). 

* At the time of this writing, when running applications on ECS, you pay only for underlying EC2 instances, with no additional charge for using ECS. However, for EKS, you pay an additional $0.10 per hour for each EKS cluster you have, along with underlying EC2 instances. 

* AWS Fargate pricing is calculated based on the vCPU, memory, and storage resources used from the time you start to download your container image until the Amazon ECS task or Amazon EKS2 pod finishes, rounded up to the nearest second.

* While cost is dependent on various factors based on the use case, Graviton2 instances have in general been able to provide better price/performance over previous generation instances. Depending on your application requirements, you may want to use additional services along with Amazon EC2, EKS, or ECS, such as Amazon Elastic Block Store  (Amazon EBS) for directly attached persistent storage, or S3 as a durable object store; each comes with its own pricing model. 

* If you do run your big data application on Amazon EC2, EKS, or ECS, you are responsible for any license fees just as you would be in your own data center. The AWS Marketplace offers many different third-party, big data software packages pre-configured to launch with a simple click of a button.

# Performance

* Performance in Amazon EC2, EKS, or ECS is driven by the instance type that you choose for your big data platform. Each instance type has a different amount of CPU, RAM, storage, IOPs, and networking capability so that you can pick the right performance level for your application requirements.

# Durability and availability

* Critical applications should be run in a cluster across multiple Availability Zones within an AWS Region so that any instance or data center failure does not affect application users. 

* For non-uptime critical applications, you can back up your application to Amazon S3 and restore to any Availability Zone in the Region if an instance or zone failure occurs. Other options exist, depending on which application you are running and the requirements, such as mirroring your application.

# Scalability and elasticity

* Auto Scaling is a service that enables you to automatically scale your Amazon EC2 capacity up or down according to conditions that you define. 

* With Auto Scaling, you can ensure that the number of EC2 instances you’re using scales up seamlessly during demand spikes to maintain performance, and scales down automatically during demand lulls to minimize costs. 

* Auto Scaling is particularly well suited for applications that experience hourly, daily, or weekly variability in usage. Auto Scaling is enabled by CloudWatch and available at no additional charge beyond CloudWatch fees.

# Interfaces

* Amazon EC2, EKS, and ECS can be managed programmatically via API, SDK, or the AWS Management Console. Metrics for compute utilization, memory utilization, storage utilization, network consumption, and read/write traffic to your instances are free of charge using the console or CloudWatch API operations.

* The interfaces for your big data analytics software that you run on top of Amazon EC2 varies based on the characteristics of the software you choose.

# Anti-patterns

* Amazon EC2 has the following anti-patterns:

 * **Managed service** – If your requirement is a managed service offering where you abstract the infrastructure layer and administration from the big data analytics, then this “do it yourself” model of managing your own analytics software on Amazon EC2 may not be the correct choice.

 * **Lack of expertise or resources** – If your organization does not have, or does not want to expend, the resources or expertise to install and manage a high-availability installation for the system in question, you should consider using the AWS equivalent such as Amazon EMR, DynamoDB, Amazon Kinesis Data Streams, or Amazon Redshift.

---

Hope this guide gives you an Introduction to Amazon Compute Services.

Let me know your thoughts in the comment section 👇
And if you haven't yet, make sure to follow me on below handles:

👋 **connect with me on [LinkedIn](https://www.linkedin.com/in/adit-modi-2a4362191/)**
🤓 **connect with me on [Twitter](https://twitter.com/adi_12_modi)**
🐱‍💻 **follow me on [github](https://github.com/AditModi)**
✍️ **Do Checkout [my blogs](https://aditmodi.hashnode.dev)** 

Like, share and follow me 🚀 for more content.

{% user aditmodi %}

---

[Reference Notes](https://docs.aws.amazon.com/whitepapers/latest/big-data-analytics-options/amazon-compute-services.html)

> **Big Data Analytics Options on AWS** is a Series containing different articles that provides a basic introduction to different Big Data Analytics Options on AWS. Each article covers the detailed guide on how each service is used for collecting, processing, storing, and analyzing big data.

* The ML Frameworks and Infrastructure level is intended for expert ML practitioners. These people are comfortable with designing their own tools and workflows to build, train, tune, and deploy models, and are accustomed to working at the framework and infrastructure level. 

* In AWS, you can use open-source ML frameworks such as TensorFlow, PyTorch, and Apache MXNet. The Deep Learning AMI and Deep Learning Containers in this level have multiple ML frameworks preinstalled that are optimized for performance. 

* This optimization means that they are always ready to be launched on powerful, ML-optimized compute infrastructure, such as Amazon EC2 P3 and P3dn instances, that provides a boost of speed and efficiency to ML workloads.

* Amazon ML can create ML models based on data stored in S3, Amazon Redshift, or Amazon RDS. Built-in wizards guide you through the steps ofinteractively exploring your data to training the ML model, evaluate the model quality, and adjust outputs to align with business goals. After a model is ready, you can request predictions in batches, or using the low-latency real-time API.

* Workloads often use services from multiple levels of the ML stack. Depending on the business use case, services and infrastructure from the different levels can be combined to satisfy multiple requirements and achieve multiple business goals. 

* For example, you can use AI services for sentiment analysis of customer reviews on your retail website, and use managed ML services to build a custom model using your own data to predict future sales.

# Ideal usage patterns

* Amazon ML is ideal for discovering patterns in your data and using these patterns to create ML models that can generate predictions on new, unseen data points. For example, you can:

 * **Enable applications to flag suspicious transactions** – Build an ML model that predicts whether a new transaction is legitimate or fraudulent.

 * **Forecast product demand** – Input historical order information to predict future order quantities.

 * **Media intelligence** – Maximize the value of media content by adding machine learning to media workflows such as search and discovery, content localization, compliance, monetization, and more.

 * **Personalize application content** – Predict which items a user will be most interested in, and retrieve these predictions from your application in real-time.

 * **Predict user activity** – Analyze user behavior to customize your website and provide a better user experience.

 * **Listen to social media** – Ingest and analyze social media feeds that potentially impact business decisions.

 * **Intelligent contact center** – Enhance your customer service experience and reduce costs by integrating ML into your contact center.

 * **Intelligent search** – Boost business productivity and customer satisfaction by delivering accurate and useful information faster from siloed and unstructured information sources across the organization.

# Cost model

* With Amazon Machine Learning services, you pay only for what you use. There are no minimum fees and no upfront commitments.

* AWS pre-trained AI Services cost model varies depending upon the AI service you are planning to integrate with your applications. For details, see pricing details of the respective AI services:

 * Amazon Comprehend

 * Amazon Forecast

 * Amazon Fraud Detector

 * Amazon Translate

 * Amazon CodeGuru

 * Amazon Textract

 * Amazon Rekognition

 * Amazon Polly

 * Amazon Lex

 * Amazon Kendra

 * Amazon Personalize

 * Amazon Transcribe

* With Amazon SageMaker, you have two choices to pay, and you only pay for what you use:

 * **On-demand pricing** is billed by the second, with no minimum fees and no upfront commitments.

 * **SageMaker Savings Plans** offer a flexible, usage-based pricing model in exchange for a commitment to a consistent amount of usage. For details, see Amazon SageMaker pricing.

* The ML Frameworks and Infrastructure level is intended for expert ML practitioners. ML training and inference workloads can exhibit characteristics that are steady state (such as hourly batch tagging of photos for a large population), spiky (such as kicking off new training jobs or search recommendations during promotional periods), or both. AWS has pricing options and solutions to help you optimize your infrastructure performance and costs.

* For details, see the AWS Machine Learning Infrastructure.

# Performance

* The time it takes to create models and to request predictions from ML models depends on the number of input data records, and the types and distribution of attributes that you specify. There are a number of principles designed to help increase performance specifically for ML workloads:

 * **Optimize compute for your ML workload** — Most ML workloads are very compute-intensive, because large amounts of vector multiplications and additions need to be performed on a multitude of data and parameters. Especially in Deep Learning, there is a need to scale to chipsets that provide larger queue depth, higher Arithmetic Logic Units and Register counts, to allow for massively parallel processing. Because of that, GPUs are the preferred processor type to train a Deep Learning model.

 * **Define latency and network bandwidth performance requirements for your models** — Some of your ML applications might require near-instantaneous inference results to satisfy your business requirements. Offering the lowest latency possible may require the removal of costly round trips to the nearest API endpoints. This reduction in latency can be achieved by running the inference directly on the device itself. This is known as Machine Learning at the Edge. A common use case for such a requirement is predictive maintenance in factories. This form of low latency and near-real-time inference at the edge allows for early indications of failure, potentially mitigating costly repairs of machinery before the failure actually happens.

 * **Continuously monitor and measure system performance** — The practice of identifying and regularly collecting key metrics related to the building, training, hosting, and running predictions against a model ensures that you are able to continuously monitor the holistic success across key evaluation criteria. To validate system level resources used to support the phases of ML workloads, it’s key to continuously collect and monitor system level resources such as compute, memory, and network. Requirements for ML workloads change in different phases, as training jobs are more memory intensive, while inference jobs are more compute intensive.

# Durability and availability

* There are key principles designed to help increase availability and durability specifically for ML workloads:

 * **Manage changes to model inputs through automation** — ML workloads have additional requirements to manage changes to the data that is used to train a model to be able to recreate the exact version of a model in the event of failure or human error. Managing versions and changes through automation provides for a reliable and consistent recovery method.

 * **Train once and deploy across environments** — When deploying the same version of an ML model across multiple accounts or environments, the same practice of build once that is applied to application code should be applied for model training. A specific version of a model should only be trained once and the output model artifacts should be utilized to deploy across multiple environments to avoid bringing in any unexpected changes to the model across environments.

# Scalability and elasticity

* There are key principles designed to help increase availability and durability specifically for ML workloads:

 * **Identify the end-to-end architecture and operational model early** — Early in the ML development lifecycle, identify the end-to-end architecture and operational model for model training and hosting. This allows for early identification of architectural and operational considerations that will be required for the development, deployment, management and integration of ML workloads.

 * **Version machine learning inputs and artifacts** — Versioned inputs and artifacts enable you to recreate artifacts for previous versions of your ML workload. Version inputs are used to create models, including training data and training source code, and model artifacts.

 * **Automate machine learning deployment pipelines** — Minimize human touch points in ML deployment pipelines to ensure that ML models are consistently and repeatedly deployed using a pipeline that defines how models move from development to production. Identify and implement a deployment strategy that satisfies the requirements of your use case and business problem. If required, include human quality gates in your pipeline to have humans evaluate if a model is ready to deploy to a target environment.

# Interfaces

* Creating a data source is as simple as adding your data to S3. To ingest data, you can use AWS Direct Connect to privately connect your data center directly to an AWS Region. 

* To physically transfer petabytes of data in batches, use AWS Snowball, or, if you have exabytes of data, use AWS Snowmobile. You can integrate your existing on-premises storage using Storage Gateway, or add cloud capabilities using AWS Snowball Edge. 

* Use Amazon Kinesis Data Firehose to collect and ingest multiple streaming-data sources.

# Anti-patterns

* Amazon ML has the following anti-patterns:

 * **Big data processing** – Data processing activities are well suited for tools like Apache Spark, which provide SQL support for data discovery, among other useful utilities. On AWS, Amazon EMR facilitates the management of Spark clusters, and enables capabilities like elastic scaling while minimizing costs through Spot Instance pricing.

 * **Real-time analytics** – Collecting, processing, and analyzing the streaming data to respond in real time are well suited for tools like Kafka. On AWS, Amazon Kinesis makes it easy to collect, process, and analyze real-time, streaming data so you can get timely insights and react quickly to new information and Amazon MSK is a fully managed service that makes it easy for you to build and run applications that use Apache Kafka to process streaming data. Apache Kafka is an open-source platform for building real-time streaming data pipelines and applications.

---

Hope this guide gives you an Introduction to Amazon Machine Learning.

Let me know your thoughts in the comment section 👇
And if you haven't yet, make sure to follow me on below handles:

👋 **connect with me on [LinkedIn](https://www.linkedin.com/in/adit-modi-2a4362191/)**
🤓 **connect with me on [Twitter](https://twitter.com/adi_12_modi)**
🐱‍💻 **follow me on [github](https://github.com/AditModi)**
✍️ **Do Checkout [my blogs](https://aditmodi.hashnode.dev)** 

Like, share and follow me 🚀 for more content.

{% user aditmodi %}

---

[Reference Notes](https://docs.aws.amazon.com/whitepapers/latest/big-data-analytics-options/amazon-machine-learning.html)