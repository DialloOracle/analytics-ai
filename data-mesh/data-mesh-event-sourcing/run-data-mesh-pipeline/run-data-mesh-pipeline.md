# Introduction & Overview

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


## Task 1: Start data feed

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

## Task 2: Observe event population in Golden Gate Stream Analytics

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

## Task 3: Query data products using Helidon microservice

1. In the firefox web browser, Open a new tab.

2. In this tab, query all of the transactions that have been approved.

    ```
    $ http://eventshelidon:8080/creditfraud
    ```



