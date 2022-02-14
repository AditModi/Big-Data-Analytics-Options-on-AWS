# Introduction

* Amazon QuickSight is a scalable, serverless, embeddable, machine learning-powered business intelligence (BI) service built for the cloud. It makes it easy for all employees within an organization to build visualizations, perform ad hoc analysis, and quickly get business insights from their data, anytime, on any device. 

* It can connect to a wide variety of datasources including flat files such as CSV and Excel, access on-premises databases including Oracle, SQL Server, MySQL, and PostgreSQL, AWS resources such as Amazon RDS databases, Amazon Redshift, Amazon Athena, and Amazon S3, and SaaS solutions such as Salesforce, ServiceNow, and Adobe Analytics. 

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/roygc54x9pfn2r5lqycd.png)
 
> **Big Data Analytics Options on AWS** is a Series containing different articles that provides a basic introduction to different Big Data Analytics Options on AWS. Each article covers the detailed guide on how each service is used for collecting, processing, storing, and analyzing big data.

* Amazon QuickSight enables organizations to scale their business analytics capabilities to hundreds of thousands of users, and delivers fast and responsive query performance by using a robust in-memory engine (SPICE).

* Amazon QuickSight is built with "SPICE" – a Super-fast, Parallel, In-memory Calculation Engine. Built from the ground up for the cloud, SPICE uses a combination of columnar storage, in-memory technologies enabled through the latest hardware innovations, and machine code generation to run interactive queries on large datasets and get rapid responses. 

* SPICE supports rich calculations to help you derive valuable insights from your analysis without worrying about provisioning or managing infrastructure. Data in SPICE is persisted until it is explicitly deleted by the user. 

* SPICE also automatically replicates data for high availability and enables Amazon QuickSight to scale to hundreds of thousands of users who can all simultaneously perform fast interactive analysis across a wide variety of AWS data sources.

* QuickSight leverages the AWS proven ML capabilities, making it easy for BI teams to perform advanced analytics (for example, what-if analyses, anomaly detection, ML-based forecasting, churn prediction, and so on) without prior data science experience. You can use QuickSight’s pre-built models, or bring your own ML models from Amazon SageMaker.

# Ideal usage patterns

* Amazon QuickSight is an ideal Business Intelligence tool, allowing end users to create visualizations that provide insight into their data to help them make better business decisions. 

* Amazon QuickSight can be used to do the following:

 * Quick interactive ad hoc exploration and optimized visualization of data

 * Create and share dashboards and KPIs to provide insight into your data

 * Create Stories, which are guided tours through specific views of an analysis and enable you to share insights and collaborate with others. They are used to convey key points, a thought process, or the evolution of an analysis for collaboration

 * Analyze and visualize data coming from logs and stored in S3

 * Analyze and visualize data from on premise databases like SQL Server, Oracle, PostGreSQL, and MySQL

 * Analyze and visualize data in various AWS resources such as Amazon RDS databases, Amazon Redshift, Amazon Athena, and Amazon S3.

 * Analyze and visualize data in software as a service (SaaS) applications such as Salesforce.

 * Analyze and visualize data in data sources that can be connected to using JDBC/ODBC connection.

 * Enhance with your QuickSight dashboard with Machine Learning Insights and Forecasts

 * Ask natural language questions on your data and have Amazon QuickSight Q automatically build your visualization

# Cost model

* Amazon QuickSight has two different editions for pricing; Standard edition and Enterprise edition.

 * The **Standard Edition** is ideal for personal data analysis and exploration, it offers a full set of features for creating and sharing data visualizations, but it does not provide some of the Enterprise security and advanced options, a comparison of the features of the two editions can be found on the Amazon QuickSight Pricing page. The Standard Edition is priced at $9/user/month for an annual subscription ($12/GB/month for the month -to month -option) with ten GB of SPICE capacity included. You can get additional SPICE capacity for $.25/GB/month.

 * The **Enterprise edition** delivers insights at scale and offers embedding options, advanced security (data encryption at rest, row and column level security, access on private VPC and on premises), ML insights, folders, and templates. It is priced at $18/author/month ($24/GB/month for the month-to-month option) with ten GB of SPICE capacity included. Readers have a per-session pricing up to $5/user/month ($.30 per session; 1 session = 30 minutes from login).

* For large-scale deployments and public embedding, there is a Session capacity pricing starting at $250 per month for 500 sessions.

# Performance

* Amazon QuickSight is built with SPICE. Built from the ground up for the cloud, SPICE uses a combination of columnar storage, in-memory technologies enabled through the latest hardware innovations, and machine code generation to run interactive queries on large datasets and get rapid responses.

# Durability and availability

* SPICE automatically replicates data for high availability and enables Amazon QuickSight to scale to hundreds of thousands of users who can all simultaneously perform fast interactive analysis across a wide variety of AWS data sources.

# Scalability and elasticity

* Amazon QuickSight is a fully managed service and it internally takes care of scaling to meet the demands of your end users. With Amazon QuickSight you don’t need to worry about scale. You can seamlessly grow your data from a few hundred megabytes to many terabytes of data without managing any infrastructure.

# Interfaces

* Amazon QuickSight can connect to a wide variety of data sources including flat files (CSV, TSV, CLF, ELF), connect to on-premises databases like SQL Server, MySQL, and PostgreSQL, and AWS data sources including Amazon RDS, Amazon Aurora, Amazon Redshift, Amazon Athena and Amazon S3, and SaaS, applications like Salesforce. 

* You can also export data from any type of chart or graph and the export contains only the data in the fields that are currently visible in the selected visualization.

* You can share an analysis, dashboard, or story by choosing Share with users and groups in your account on the application bar from the Amazon QuickSight service interface. You can select the recipients (email address, username, or group name), permission levels, and other options, before sharing the content with others.

# Anti-patterns

* Amazon Quicksight has the following anti-patterns:

 * **Highly formatted canned Reports** — Amazon QuickSight is uited for ad hoc query, analysis, and visualization of data. For highly formatted reports such as formatted financial statements, consider using a different tool.

 * **ETL** — While Amazon QuickSight can perform some transformations, it is not a full-fledged ETL tool. AWS offers AWS Glue, which is a fully managed ETL service that makes it easy for customers to prepare and load their data for analytics.


---

Hope this guide gives you an Introduction to Amazon QuickSight.

Let me know your thoughts in the comment section 👇
And if you haven't yet, make sure to follow me on below handles:

👋 **connect with me on [LinkedIn](https://www.linkedin.com/in/adit-modi-2a4362191/)**
🤓 **connect with me on [Twitter](https://twitter.com/adi_12_modi)**
🐱‍💻 **follow me on [github](https://github.com/AditModi)**
✍️ **Do Checkout [my blogs](https://aditmodi.hashnode.dev)** 

Like, share and follow me 🚀 for more content.

{% user aditmodi %}

---

[Reference Notes](https://docs.aws.amazon.com/whitepapers/latest/big-data-analytics-options/amazon-quicksight.html)