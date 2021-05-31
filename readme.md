#TRIPS_MANAGEMENT_SERVICES

TRIPS_MANAGEMENT_SERVICES consist of microservices that communicates with each other asynchronously through Apache Kafka topics.

We use the Micronaut Framework, which provides a dedicated library for integration with Kafka. Let’s take a brief look at 
the architecture of our sample system. We have 4 microservices: order-service, trip-service, driver-service, and passenger-service. 
The implementation of these applications is very simple. All of them have in-memory storage and connect to the same Kafka instance.

A primary goal of our system is to arrange a trip for customers. The order-service application also acts as a gateway. 
It is receiving requests from customers, saving history, and sending events to orders topic. All the other microservices
are listening on this topic and processing orders sent by order-service. Each microservice has its own dedicated topic, 
where it sends events with information about changes. Such events are received by some other microservices.

Technology used
----------------------------------------
Java 8
REST API
Micronaut 
Swagger 
Lombok
Docker
Maven
Apache kafka 
Kafdrop

