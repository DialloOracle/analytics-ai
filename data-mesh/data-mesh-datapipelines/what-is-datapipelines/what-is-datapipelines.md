# What is Data Pipelines?

## Data Pipelines

Application modernization is the process of updating older applications to newer languages, frameworks, and deployment models. To be specific, app modernization includes, but is not limited to: deploying applciations to containers, deploying applications to a cloud platform, and refactoring monolithic applications to microservices. Typically, one will see a combination of these processes in their modernization efforts. The reasons for doing this will vary from organization to organization, and many of them will only adopt certain facets of modernization, but generally, some of the reasons for modernization include: scalability benefits, faster time-to-deployment, and standard infrastructure platforms. This workshop will explore some of the benefits of adopting app modernization in a Data Mesh architecture. 

Data Pipelines is a modern architecture that facilitates the preparation and transformation of data across different data stages or data zones. Using data refinement, downstream analytics can produce data products. This process uses an independently governed data pipeline layer that works with analytics data stores. This produces self-service data discovery and data preparation. Governance is enabled across domains for data resources. Data products are formatted according to data transformation rules such as streaming or ETL. And then, policies are used to ensure consistency across data verification.

These data pipelines should be capable to work across different physical data stores (such as marts, warehouses, lakes etc) or as a “pushdown data stream” within analytic data platforms that support streaming data, such as Apache Spark and other data lake house technologies.

## Data Pipelines in this workshop

This workshop will show you how to use streaming data pipelines to connect data stores to analytics data platforms. Taking raw data from a data lakehouse and enriching with customer data, GoldenGate Microservices is used to monitor credit card transactions with the help of GoldenGate Streaming Analytics. A Machine Learning model is used to predict credit ratings for risky or good credit patterns in real time across Geo-Locations. Data pipelines form across four main pathways: raw data, fraudulent data, credit card increase data, and analytics data. 

## Acknowledgements

- **Author**- Nicholas Cusato, North American Specialist Hub
- **Last Updated By/Date** - Nicholas Cusato, Stephen Stuart, Alpha Diallo, Mathew McDaniel, September 2023
