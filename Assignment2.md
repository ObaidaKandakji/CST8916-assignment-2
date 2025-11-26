# Cloud Service Providers Comparison Report

## 1. Executive Summary

This report compares three major cloud service providers: Amazon Web Services (AWS), Microsoft Azure, and Google Cloud Platform (GCP), with a focus on services that support remote data access and real time applications. The comparison covers RESTful and GraphQL APIs, WebSocket based communication, data streaming, and real time analytics, and it also considers cost, performance, and ease of integration.

From a feature point of view, AWS offers the broadest range of managed services. It provides mature tools for APIs, managed GraphQL through AppSync, WebSocket APIs, and Kinesis based streaming with Apache Flink for analytics. Azure is strongest for organisations that already use Microsoft technologies. Its API Management, Web PubSub and SignalR, Event Hubs, and Stream Analytics integrate closely with Azure Active Directory, Microsoft 365, and hybrid on premises environments. GCP focuses on data and analytics. It combines API Gateway with Pub/Sub, Dataflow, and BigQuery and is attractive for teams that prefer container based and open source tools.

The key finding is that no single provider is the absolute best in every situation. For greenfield web and mobile applications that need a wide set of real time features and global reach, AWS is usually the most flexible choice. For enterprises that are heavily invested in Microsoft, Azure is often the most practical and cost effective path. For data intensive workloads that prioritise streaming analytics and large scale querying, GCP provides strong capabilities. Overall, the recommendation is to align the chosen cloud platform with existing skills, tools, and long term workload patterns instead of selecting only on individual services.

## 2. Introduction

The purpose of this report is to compare AWS, Azure, and GCP in the context of remote data access and real time applications. Many organisations now rely on applications that must serve users in different locations and update interfaces almost instantly. This creates a need for reliable APIs, low latency communication, high volume data ingestion, and continuous analytics.

From my research, all three providers supply the same basic building blocks. They offer virtual machines, managed databases, object storage, serverless computing, and global networking. On top of that, they add more specialised services that target modern patterns such as RESTful APIs, GraphQL, WebSockets, event streaming, and stream processing.

AWS is one of the oldest and largest cloud platforms and is known for its very wide portfolio of services. Azure is closely linked to the Microsoft ecosystem and is popular with enterprises that use Windows, Office, and on premises Active Directory. GCP is Google’s cloud platform and has a strong reputation for data analytics and container based workloads. By comparing these providers across specific service categories and by looking at two example use cases, this report aims to highlight which platform is the best fit in different situations.

## 3. Service Comparison

### 3.0 Summary Table


| Category               | AWS                                          | Azure                                            | GCP                                               | Notes                                                  |
|------------------------|----------------------------------------------|--------------------------------------------------|---------------------------------------------------|--------------------------------------------------------------|
| RESTful APIs           | API Gateway (REST and HTTP)                  | API Management (APIM)                            | API Gateway and Apigee                            | All provide managed gateways for RESTful services            |
| GraphQL                | AppSync (managed GraphQL)                    | APIM and Data API Builder                        | Custom GraphQL on Cloud Run or GKE plus Apigee    | Only AWS has a dedicated managed GraphQL service             |
| WebSockets             | API Gateway WebSocket APIs                   | Web PubSub and Azure SignalR Service             | WebSockets on Cloud Run or GKE                    | All support real time communication with automatic scaling   |
| Data streaming         | Kinesis and Amazon MSK (managed Kafka)       | Event Hubs                                       | Pub/Sub                                           | All handle high throughput event ingestion                   |
| Stream analytics       | Managed Apache Flink for streaming analytics | Azure Stream Analytics                           | Dataflow running Apache Beam                      | All integrate with their own data and storage services       |

### 3a. RESTful API Services

AWS uses Amazon API Gateway for REST and HTTP APIs, with pay per request pricing and deep integration with Lambda and other backends.  

Azure offers Azure API Management, which combines a gateway with policies and a developer portal, and uses tier based pricing.  

GCP provides Cloud API Gateway for simple gateways and Apigee for full API management, both charged mainly per API call.

### 3b. GraphQL Services

AWS AppSync is a managed GraphQL service that connects directly to DynamoDB, Lambda, and other AWS services.  

Azure supports GraphQL through API Management and Data API Builder, which can generate GraphQL from databases.  

On GCP, GraphQL servers such as Apollo or Hasura are usually deployed on Cloud Run or GKE, optionally behind Apigee.

### 3c. WebSocket Services

AWS supports WebSockets through API Gateway WebSocket APIs, which manage connections and route messages to backends.  

Azure provides Azure Web PubSub and Azure SignalR Service for large scale real time messaging.  

GCP lets teams run WebSocket applications on Cloud Run or GKE, where containers scale automatically with traffic.

### 3d. Data Streaming Services

AWS offers Kinesis Data Streams and Amazon MSK for high volume event streaming.  

Azure uses Event Hubs as its main event ingestion service for logs, telemetry, and IoT data.  

GCP uses Pub/Sub as a fully managed publish subscribe service for streaming pipelines.

### 3e. Stream Analytics

On AWS, managed Apache Flink processes streaming data from Kinesis or MSK in real time.  

On Azure, Stream Analytics runs SQL like queries over data from Event Hubs or IoT Hub.  

On GCP, Dataflow runs Apache Beam pipelines in streaming mode, often reading from Pub/Sub and writing to BigQuery.


## 4. Use Case Analysis

### Scenario 1: Global real time collaboration tool

A company wants to build a browser based collaboration app where users can edit documents and see updates in real time. The app needs REST and GraphQL APIs, WebSockets, and data streaming for events such as presence and typing indicators. Users will connect from many regions.

For this scenario, AWS is the most suitable choice. API Gateway, AppSync, WebSocket APIs, and Kinesis work together to support real time features with global reach. Serverless options such as Lambda and HTTP APIs help keep costs manageable early on, and AWS has a large ecosystem of SDKs and tools for web and mobile development.

### Scenario 2: Real time IoT analytics for manufacturing

A manufacturing company wants to collect data from thousands of sensors in several factories, run near real time analytics, and present dashboards to engineers. The company already uses Microsoft 365 and runs Windows servers on premises.

Here, Azure is the best fit. Azure IoT Hub and Event Hubs can ingest sensor data, while Azure Stream Analytics can process it and send results to Power BI or Azure SQL Database. Integration with Azure Active Directory and existing Microsoft tools reduces configuration effort and training. Pricing is relatively predictable when using tier based services and reserved capacity.

### Use case summary table

| Scenario                                      | Recommended CSP | Cost                                     | Performance                               | Integration and ecosystem                                   |
|-----------------------------------------------|-----------------|------------------------------------------|-------------------------------------------|-------------------------------------------------------------|
| Global real time collaboration tool           | AWS             | Good use of serverless pay per use       | Strong global presence and low latency    | Rich support for web and mobile applications                |
| Real time IoT analytics for manufacturing     | Azure           | Tier based pricing fits stable workloads | Optimised for event and IoT data          | Deep integration with Microsoft 365 and on premises systems |

## 5. Conclusion

In this report I compared AWS, Azure, and GCP and looked at how well they support remote data access and real time applications. All three platforms provide the main building blocks, including RESTful APIs, some level of GraphQL support, WebSockets, data streaming services, and stream analytics. The real difference is how these services work together and which kinds of organisations they suit best.

From my research, AWS stands out because it has the widest range of managed services. It is a strong choice for new web and mobile applications that need global reach, flexible real time features, and many options for integration. Azure seems most attractive for organisations that already use Microsoft tools. Its API, streaming, and analytics services connect closely with Microsoft 365, Active Directory, and on premises Windows servers. 

GCP looks strongest for data and analytics focused work, especially for teams that like container based and open source tools and want tight integration with BigQuery and Dataflow.

Overall, there is no single best provider. The choice should match the organisation’s skills, existing systems, and long term plans.

## 6. References

https://docs.aws.amazon.com/whitepapers/latest/aws-overview/introduction.html

https://docs.cloud.google.com/docs/overview

https://learn.microsoft.com/en-us/azure/?product=popular

## AI Usage Disclosure

An AI tool was used to help with grammar, formatting and the executive Summary. All ideas and arguments in this report are my own work.