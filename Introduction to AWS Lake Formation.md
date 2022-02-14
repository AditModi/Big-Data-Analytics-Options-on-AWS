# Introduction

* AWS Lake Formation is an integrated data lake service that makes it easy for you to ingest, clean, catalog, transform, and secure your data and make it available for analysis and machine learning. 

* Lake Formation gives you a central console where you can discover data sources, set up transformation jobs to move data to an S3 data lake, remove duplicates and match records, catalog data for access by analytic tools, configure data access and security policies, and audit and control access from AWS analytic and machine learning services.

* Lake Formation automatically manages access to the registered data in S3 via services including AWS Glue, Amazon Athena, Amazon Redshift, Amazon EMR Notebooks and Zeppelin notebooks with Apache Spark, and Amazon QuickSight to ensure compliance with your defined policies. 

* If you’ve set up transformation jobs spanning AWS services, Lake Formation configures the flows, centralizes their orchestration, and lets you monitor the running of your jobs. With Lake Formation, you can configure and manage your data lake without manually integrating multiple underlying AWS services.

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/lc05pwt21g068zl5b8zl.png) 
 
> **Big Data Analytics Options on AWS** is a Series containing different articles that provides a basic introduction to different Big Data Analytics Options on AWS. Each article covers the detailed guide on how each service is used for collecting, processing, storing, and analyzing big data.

# Ideal usage patterns

* AWS Lake Formation helps you collect and catalog data from databases and object storage, move the data into your new S3 data lake, clean and classify your data using machine learning algorithms, and secure access to your sensitive data. 

* Your users can access a centralized data catalog which describes available datasets and their appropriate usage. Using AWS Lake Formation gives you the following benefits:

 * **Build data lakes quickly**

     * Lake Formation blueprints simplify the deployment of ingestion workflow via a simple interface.

     * Simply point Lake Formation at your data sources, and Lake Formation crawls those sources and moves the data into your new S3 data lake.

     * Lake Formation has built-in machine learning to deduplicate and find matching records (two entries that refer to the same thing) to increase data quality.

 * **Simplify security management**

     * Centrally define security, governance, and auditing policies in one place.

     * You can define security policy-based rules for your users and applications by role in Lake Formation, and integration with AWS Identity and Access Management (AWS IAM) authenticates those users and roles.

     * With tag-based access control, data stewards can define a tag ontology based on data classification, and grant access based on tags to IAM principals and SAML principals or groups.

     * Enforce encryption leveraging the encryption capabilities of S3 for data in your data lake.

     * Provides comprehensive audit logs with CloudTrail to monitor access and show compliance with centrally defined policies.

 * **Provide self-service access to data**

     * Label your data with business metadata. Designate data owners, such as data stewards and business units, by adding a field in table properties as “custom attributes”.

     * Specify, grant, and revoke permissions on tables defined in the central Data Catalog. The same Data Catalog is available for multiple accounts, groups, and services.

     * Search for relevant data by name, contents, sensitivity, or other any other custom labels you have defined.

 * **Integration**

     * Integration with data access services like Amazon Athena, Amazon EMR, Amazon Redshift, and Amazon QuickSight.

 * **Serverless**

     * No infrastructure to provision or manage.

# Cost model

* There is no additional charge for using features in Lake Formation. Lake Formation helps you build and manage data lakes where your data in stored in S3. It builds on capabilities available in AWS Glue and uses the AWS Glue Data Catalog, jobs, and crawlers. 

* It also integrates with services like AWS CloudTrail, AWS IAM, Amazon CloudWatch, Amazon Athena, Amazon EMR, Amazon Redshift, and others.

*Standard usage rates for these services will apply based on pricing for these services.* 

# Performance

* AWS Lake Formation uses AWS Glue as a transformation engine. *Refer to the AWS Lake Formation: How it Works section of the Lake Formation Developer Guide.* 

# Durability and availability

* AWS Lake Formation leverage S3 as data lake storage, designed to provide 99.999999999% of data durability of objects over a given year. It creates and stores copies of all S3 objects across multiple systems. 

* This means your data is available when you need it, and protected against failures, errors, and threats. The AWS Glue service is fully managed. It provides status for each job and pushes all notifications to Amazon CloudWatch Events. You can setup SNS notifications using CloudWatch actions to be informed of job failures or completions.

# Scalability and elasticity

* AWS Lake Formation uses AWS Glue, which provides a managed ETL service that runs on a Serverless ApacheSpark environment. This enables you to focus on your ETL job and not worry about configuring and managing the underlying compute resources. 

* AWS Glue works on top of the Apache Spark environment to provide a scale-out run environment for your datat ransformation jobs.

# Interfaces

* Lake Formation provides a console to manage your data lake locations, data catalog, access privileges, and deploy blueprints. It also provides APIs and a CLI to integrate Lake Formation functionality into your custom applications. 

* Java and C++ SDKs are available to enable you to integrate your own data engines with Lake Formation. Lake Formation manages query access from AWS Glue, Athena, Amazon Redshift, EMR Notebooks, and Zeppelin notebooks for EMR with Apache Spark through a unified security model and permissions.

* You can use third-party business applications like Tableau and Looker to connect to your AWS data sources through services like Athena or Amazon Redshift. 

* Access to data is managed by the underlying data catalog, so regardless of which application you use, you are assured that access to your data is governed and controlled.

# Anti-patterns

* AWS Lake Formation has the following anti-patterns:

 * **Managing unstructured data** – AWS Lake Formation does not manage security for unstructured objects as document (PDF, Word), images, or videos.

 * **Business catalog** – Lake Formation helps label your data with business metadata and designate data owners such as data stewards and business units by adding a field in table properties as “custom attributes”. For advanced use cases, consider integrating a Partner solution from the AWS Marketplace.

 * **Managing permission for open source and third-party big data components** — AWS Lake Formation is not integrated with Presto, HBase and other EMR components not specified in the previous Interface section of this chapter. It is also not integrated with third party applications such as Trino or Databricks.

 * **Real-time analytics** – AWS Lake Formation is not integrated with Amazon Kinesis or OpenSearch Service. If you need to manage a real-time analytics pipeline or dashboard, you will have to manage privileges in a traditional way.


---

Hope this guide gives you an Introduction to AWS Lake Formation.

Let me know your thoughts in the comment section 👇
And if you haven't yet, make sure to follow me on below handles:

👋 **connect with me on [LinkedIn](https://www.linkedin.com/in/adit-modi-2a4362191/)**
🤓 **connect with me on [Twitter](https://twitter.com/adi_12_modi)**
🐱‍💻 **follow me on [github](https://github.com/AditModi)**
✍️ **Do Checkout [my blogs](https://aditmodi.hashnode.dev)** 

Like, share and follow me 🚀 for more content.

{% user aditmodi %}

---

[Reference Notes](https://docs.aws.amazon.com/whitepapers/latest/big-data-analytics-options/aws-lake-formation.html)