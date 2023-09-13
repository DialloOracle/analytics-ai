# Set up Event Sourcing pipeline

## Introduction

This hands-on lab is designed to demonstrate how Oracle GoldenGate 19c Microservices can be used to setup a replication environment by a mix of web page, shell scripts and Rest API interfaces.  

The labs will walk the end-user through how to add components of Oracle GoldenGate replication.

*Estimated Lab Time*: 30 mins

### About Oracle GoldenGate Microservices
Oracle GoldenGate offers high-performance, fault-tolerant, easy-to-use, and flexible real- time data streaming platform for big data environments. It easily extends customers’ real-time data integration architectures to big data systems without impacting the performance of the source systems and enables timely business insight for better decision making. This workshop focuses on **GoldenGate Real Time Data Capture** demonstrating four scenarios that you can use (both on-premise and in the cloud) to capture real time data changes from your sources.

## Task 1: Create Event Log pipeline

For the purpose of this workshop, all data sources, streams, and targets have been preconfigured for your convenience. Your job will be to configure the pipeline and create the transformations that the events will undergo.

1. To start, access the Golden Gate Stream Analytics console in the Firefox web browser, then click **Catalog**.

    ![](images/access-ggsa.png)

2. Once in the catalog, you will see numerous resources, ranging from streams, targets. In the top-right, click on **Create New Item**. Once the dropdown appears, click **Pipeline**.

3. When the following screen appears, Populate the fields with the following values:

    - **Name**: createEventLog
    - **Display Name**: createEventLog
    - **Description**: *optional*
    - **Tags**: *optional*
    - **Stream**: EventLogStream

    ![](images/create-pipeline.png)

4. Click **Save*.

5. You should now be within the **createEventLog** pipeline and should see the following view.

    ![](images/pipeline-view.png)

## Task 2: Create Event Handler pipeline

1. Select Done to return to the **Catalog**.

2. Once again, in the top-right, click on **Create New Item**. Once the dropdown appears, click **Pipeline**.

3. When the following screen appears, Populate the fields with the following values:

    - **Name**: EventHandler
    - **Display Name**: EventHandler
    - **Description**: *optional*
    - **Tags**: *optional*
    - **Stream**: EventLogStream [ask about this, may change]

    ![](images/create-pipeline.png)

4. Click **Save*.

## Acknowledgements

- **Author**- Matthew McDaniel, North America Specialist Hub
- **Last Updated By/Date** - Alpha Diallo, Nicholas Cusato, July 2023
