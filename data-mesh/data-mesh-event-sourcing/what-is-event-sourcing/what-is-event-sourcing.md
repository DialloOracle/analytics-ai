# What is Event Sourcing?

## Event Sourcing

Event Sourcing is the process of exchanging data payloads with other payloads using microservices. A modern ‘service mesh’ style platform uses events for data interchange. Rather than depending on batch processing in the data tier, data payloads flow continuously when events happen in the application or data store. This workshop will explore event sourcing of payloads using CQRS in a data mesh architecture. 

## What is CQRS

Simply put, CQRS (Command Query Responsibility Segregation) is a software architecture pattern that seperates reads and writes into two separate models. An example of this could be two separate data sources, one which is a read-only database, and the only a write database. Synchronization between these two data stores can be accomplished through an event log (Kafka, for instance). The benefit of this is that, in conjunction with the event sourcing pattern, we can recreate our data stores fairly easily by utlizing the event log, which is updated on a transaction-by-transaction basis.

## Event Sourcing in this workshop

Event Sourcing is an architectural pattern that emphasizes storing changes to domain objects. In effect, this means we can maintain an event log where we can query the changes a domain object has undergone. In our use case, the events that we will be tracking are credit card transactions. Once a transaction is made, it will be picked up by a Kafka Topic and placed within an event log. Following this, the event will be sent through a Golden Gate Stream Analytics pipeline where it will undergo a transformation via filtering and analysis. During this process, we will run the event through a machine learning via Oracle Machine Learning, which will determine whether or not the transaction is fraudulent. 

## Acknowledgements

- **Author**- Matthew McDaniel, North America Specialist Hub
- **Last Updated By/Date** - Alpha Diallo, Nicholas Cusato, July 2023
