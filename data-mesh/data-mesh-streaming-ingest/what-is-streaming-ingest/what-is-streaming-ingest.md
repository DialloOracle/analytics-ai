# What is Streaming Ingest?

## Streaming Ingest

Event Sourcing is the process of exchanging data payloads with other payloads using microservices. A modern ‘service mesh’ style platform uses events for data interchange. Rather than depending on batch processing in the data tier, data payloads flow continuously when events happen in the application or data store. This workshop will explore event sourcing of payloads using CQRS in a data mesh architecture. 

## Streaming Ingest in this workshop

Event Sourcing is an architectural pattern that emphasizes storing changes to domain objects. In effect, this means we can maintain an event log where we can query the changes a domain object has undergone. In our use case, the events that we will be tracking are credit card transactions. Once a transaction is made, it will be picked up by a Kafka Topic and placed within an event log. Following this, the event will be sent through a Golden Gate Stream Analytics pipeline where it will undergo a transformation via filtering and analysis. During this process, we will run the event through a machine learning via Oracle Machine Learning, which will determine whether or not the transaction is fraudulent. 

In this lab, you will explore an IoT use case using streaming ingest to process real-time IoT data streams of customers to promote events to encourage more spending. You will identify if a customer is likely to be a spender.

## Acknowledgements

- **Author**- Matthew McDaniel, North America Specialist Hub
- **Last Updated By/Date** - Alpha Diallo, Nicholas Cusato, July 2023
