# IBM MQ
## Introduction
You can use IBM MQ to enable applications to communicate at different times and in many diverse computing environments.

What is IBM MQ?

   - IBM MQ is messaging for applications. It sends messages across networks of diverse components. Your application connects to IBM MQ to send or receive a message. IBM MQ handles the different processors, operating systems, subsystems, and communication protocols it encounters in transferring the message. If a connection or a processor is temporarily unavailable, IBM MQ queues the message and forwards it when the connection is back online.

   - An application developer has a choice of programming interfaces, and programming languages to connect to IBM MQ.
   
   - IBM MQ is messaging and queuing middleware, with point-to-point,publish/subscribe, and file transfer modes of operation. Applications can publish messages to many subscribers over multicast.


[Return to main Lab section](../index.md#lab-section)


## Lab Abstracts

|  Subject                            | Description                                            |                                                               
|-----------------------------|------------------------------------------------------------------------------------------------------------| 
| [EnvSetup](Msg-Pre-lab/mqsetup/mq_setup_steps.md) | MQ lab environment Setup - download MQ lab artifacts                                         
|--------------------------------|-----------------------------------------------------------------|
| [Lab 1a](Lab_1a-CRR/Readme.md) | NEW MQ Native HA Queue Manager running in containers platforms  | 
|--------------------------------|-----------------------------------------------------------------|
| [Lab 1b](Lab_1b-CRR/Readme.md)   | NEW MQ Native HA Cross Region Replication between clusters    | 
|--------------------------------|-----------------------------------------------------------------|
| [Lab 2](Lab_2/ReadMe.md)       | Streaming Queues for MQ                                       |  
|--------------------------------|-----------------------------------------------------------------|
| [Lab 3](Lab_3/Readme.md)       | Uniform Cluster and Application Load Balancing                  |
|--------------------------------|-----------------------------------------------------------------|

[Return to main lab section](../index.md#lab-section)
