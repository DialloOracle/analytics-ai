<<<<<<< HEAD
# Run Data Mesh Pipeline

This lab will walk you through how to run the data mesh pipeline.

### Objectives

In this lab, you will
- Run the transaction feed script
- View the transactions as they are picked up by Golden Gate.
- Fetch data products via Helidon microservice
- View analytical views via OAS

### Prerequisites
For this lab, you must have have access to:
- The `dmsafeevents` instance
- The `eventshelidon` instance
- Access to GoldenGate Stream Analytics via a web browser


## Task 1: Run the transaction feed script

1. In the terminal, start the data feed with the following command.

    ```
    $ <PATH_TO_FEED>
    ```

2. Now, go to the terminal session labelled *eventshelidon*.

3. Run the Helidon microservice.

    ```
    $ java -jar $PATH_TO_HELIDON_JAR
    ```

    The microservice will now be running on port 8080.

## Task 2: View the transactions as they are picked up by Golden Gate.

1. Go to the Golden Gate Streaming Analytics console in Firefoz.

2. Hover over `createEventLog`, click on the button that says *Publish*.

3. Hover over the **EventHandler** pipeline. Click the button that says *Publish*

4. Now, both pipelines are published and will be picking up events from the feed script that was run earlier.

5. Click on **createEventLog**

6. In this screen, you can see the events as they are picked up by GGSA.

7. Go through each individual stage and observe the transformations being performed on the events.

8. Go back to the **Catalog** page.

9. Click on the **EventHandler** pipeline

10. Observe the events being picked up from the **EventLog**.

11. Go through each individual stage in the pipeline. 

## Task 3: Fetch data products via Helidon microservice

1. In the firefox web browser, Open a new tab.

2. In this tab, query all of the transactions that have been approved.

    ```
    $ http://eventshelidon:8080/creditfraud
    ```

## Task 4: View analytical views via OAS



## Acknowledgements

- **Author**- Matthew McDaniel, North America Specialist Hub
- **Last Updated By/Date** - Alpha Diallo, Nicholas Cusato, July 2023

=======
# Introduction

## About Oracle Database 19c

Oracle Database 19c provides the most advanced SQL engine on the planet. It complies with the latest ISO SQL standard, making it not only the most comprehensive database but also the most open one. It supports highly sophisticated analytics alongside and with no impact on OLTP workloads, eliminating the need to develop and orchestrate complex, fragile, and inconsistent data movement between different specialized data stores. Oracle’s SQL engine ships with integrated machine learning algorithms and allows developers to easily apply them on the data directly, hence moving the computation to the data—rather than having to pull the data out of the database and perform the calculation within the application. Using this capability, developers can create real-time prediction models directly on the data itself and act on insights more quickly and easily than ever before.

[](youtube:LcsPSJrZDrI)

Oracle Database 19c supports fully consistent data with ACID transaction guarantees and consistent queries. This greatly simplifies application development compared to NoSQL stores. Native JSON support makes up a cornerstone for flexible schema support and Internet of Things (IoT)workloads, enabling developers to simply load JSON documents into the database natively and analyze them later on, with the full power of Oracle SQL. Oracle’s PL/SQL engine is yet another powerful tool for bringing computations to the data and providing an easy and standardized interface to them by using simple SQL function or procedure calls. Interfaces such as REST allow for easy communication and integration with Oracle Database. These can be created automatically on top of tables, as well as stored procedures, giving developers the flexibility on how and what data to expose to consuming services.

Extend this with the move to autonomy provided by Oracle Autonomous Database, a self-driving, self-securing, and self-repairing approach where the database itself decides on the steps to perform for the best of the user's workload or data. Machine learning algorithms are used to help the database to decide how to tune a workload, how to secure the data, and how to take countermeasures to preserve the agreed-on SLA levels.

With the Oracle Autonomous Database, developers can fully concentrate on the applications they write and the business’s requirements, rather than having to think about the data tier. And to make this even easier the Oracle Autonomous Database environment can be provisioned in minutes with a few simple clicks or an API call to the Oracle Cloud.

## About the Oracle Database 19c New Features Workshop

This workshop lets you try out new features in Oracle Database 19c. All the labs are independent of each other, so you don't need to do them in any particular order. If needed, a lab starts with instructions on how to prepare your environment, and ends with instructions on how to restore your environment back to its original state. For most lab steps, you enter a command in the terminal window. For database actions, you use SQL*Plus.

> **Note**: Currently, this workshop is not supported in an Always Free environment. If you are using the LiveLabs environment (green button), please note that the **Install Oracle Database 19c with Automatic Root Script Execution** lab is not available.

### General Database Overall Enhancement Labs

The following general database overall enhancement labs are available:

- Install Oracle Database 19c with Automatic Root Script Execution
- Clone a PDB from a Remote CDB by Using DBCA in Silent Mode
- Relocate a PDB to a Remote CDB by Using DBCA in Silent Mode
- Duplicate a CDB by Using DBCA in Silent Mode
- Decrease the Transportable Tablespace (TTS) Import and Export Time
- Omit the Column Encryption Attribute During Import
- Use RMAN to Connect to a PDB to Use the Recovery Catalog
- Explore Automatic Deletion of Flashback Logs

If you would like to watch us do the general enhancement labs, click [here](https://youtu.be/Kdw7uugt0-E).

### Security Enhancement Labs

The following security enhancement labs are available:

- Explore Oracle-Supplied Schema-Only Accounts
- Protect Application Data by Using Database Vault Operations Control
- Restrict Users from Executing the AUDIT POLICY and NOAUDIT POLICY SQL Commands by Using Oracle Database Vault Command Rules
- Audit Direct User Activities
- Handle Operations on Oracle-Managed and User-Managed Tablespaces Encrypted in TDE

## Acknowledgements

- **Author**- Jody Glover, Principal User Assistance Developer, Database Development
- **Last Updated By/Date** - Matthew McDaniel, Austin Specialist Hub, February 24 2022
>>>>>>> upstream/main
