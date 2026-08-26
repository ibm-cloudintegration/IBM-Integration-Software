## IBM Event Automation
Get hands on building Event Automation flows.  Define business scenarios in an intuitive, easy-to-use authoring canvas. Detect whenever they arise and start acting in real-time when it matters the most. 

[Return to kafka main page](../index.md#lab-abstracts)

## Lab Abstracts

|  Subject                            | Description                                            |                                                               
|-------------------------|------------------------------------------------------------------------------------------------------------|
| [New Customer Orders](NewCustomerOrders/index.md)       |**Discover topics and Filter events** For this scenario, you need a source of order events. A good place to discover sources of event streams to process is the catalog in Event Endpoint Management.  <br>When processing events, we can use filter operations to select a subset that we want to use. Filtering works on individual events in the stream.
|-------------------------|------------------------------------------------------------------------------------------------------------|
| [Identify Suspicious Orders](IdentifySuspiciousOrders/index.md)       |**Join events** Join related events that occur within a time window.  **Event destination** Save the results to a Kafka Topic in Event Streams so that future automatic actions can be done based on event triggers 
|-------------------------|------------------------------------------------------------------------------------------------------------|
| [Payment from New Customers](PaymentNewCustomer/Lab_2/ReadMe.md)       |**Event destination** The order management system and its payment gateway exchange customer orders over IBM MQ. The integration team will tap into this communication, clone each of the orders and publish the messages into an event stream.
|-------------------------|------------------------------------------------------------------------------------------------------------|
| [Enrich Topic with data from DB](EnrichWithRefData/ReadMe.md)       |**Enrich events with reference data** Track the hourly number of events captured by door sensors in each building and enrich with data from DataBase.


[Return to kafka main page](../index.md#lab-abstracts)