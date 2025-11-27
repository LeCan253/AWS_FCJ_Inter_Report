---
title: "Worklog Week 6"
date: 2025-10-13
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---


### Week 6 Objectives:

* Use AWS Glue as the data catalog. Use Amazon Athena to query data in the data lake and Amazon QuickSight for visualization.
* Learn about Amazon DynamoDB.
* Learn AWS Glue & Amazon Athena.
* Analytics on AWS workshop.
* Module 07

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                   | Start Date | End Date     | Resources                            |
| --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | ------------- | ------------------------------------- |
| 2   | **Task**: Watch and practice Module 07 - Lab 35 on AWS Study Group YouTube <br> **Practice:** <br>&emsp; + Module07-LAB 35: DataLake on AWS                                                                                       | 13/10/2025 | 13/10/2025    | <https://000035.awsstudygroup.com/vi/1-introduce/> |
| 3   | **Task**: Watch and practice Module 07 - Lab 39 on AWS Study Group YouTube <br> **Practice:** <br>&emsp; + Module07-LAB 39: Amazon DynamoDB Immersion Day                                                                  | 14/10/2025 | 14/10/2025    | <https://000039.awsstudygroup.com/vi/> |
| 4   | **Task**: Watch and practice Module 07 - Lab 40 on AWS Study Group YouTube <br> **Practice:** <br>&emsp; + Module07-LAB 40: AWS Glue & Amazon Athena                                                                        | 15/10/2025 | 15/10/2025    | <https://000040.awsstudygroup.com/vi/> |
| 5   | **Task**: Watch and practice Module 07 - Lab 60 on AWS Study Group YouTube <br> **Practice:** <br>&emsp; + Module07-LAB 60: Working with Amazon DynamoDB                                                                    | 16/10/2025 | 16/10/2025    | <https://000060.awsstudygroup.com/vi/1-using-tags> |
| 6   | **Task**: Watch and practice Module 07 - Lab 72 on AWS Study Group YouTube <br> **Practice:** <br>&emsp; + Module07-LAB 72: Analytics on AWS workshop                                                                        | 17/10/2025 | 17/10/2025    | <https://000072.awsstudygroup.com/vi/1-using-tags> |


### Week 6 Results:

A Data Lake is a concept related to Big Data. A Data Lake is simply a repository that stores raw (unprocessed) data waiting to be processed, analyzed and turned into insights.

Data Lake characteristics:
  * Collect everything – stores raw or processed data over long periods.
  * Multi-user – allows many users to refine, explore and enrich data.
  * Flexible access – supports many access patterns on shared infrastructure: batch, interactive, online, search, in-memory and other processing tools.

Learnings about DynamoDB
  * https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Introduction.html

Amazon DynamoDB is a fully managed NoSQL database service that delivers fast, predictable performance with seamless scalability. DynamoDB reduces the operational burden of running and scaling a distributed database by handling hardware provisioning, setup and configuration, replication, software patching and cluster scaling. DynamoDB also provides encryption at rest.

  * DynamoDB creates database tables that can store and retrieve any amount of data and serve any level of request traffic. You can scale capacity up or down for your tables without downtime or performance degradation.
  * DynamoDB provides on-demand backups. You can create full backups of your tables for long-term retention and compliance.
  * You can enable point-in-time recovery (PITR) for DynamoDB tables to protect against accidental writes or deletes. With PITR you can restore a table to any point in the last 35 days.
  * DynamoDB supports automatic expiration of items (time-to-live) to reduce storage usage and costs for stale data.

Analytics on AWS Workshop

* 1 Design a serverless Data Lake architecture.
* 2 Build data pipelines and a Data Lake using Amazon S3 for storage.
* 3 Use Amazon Kinesis for real-time streaming data ingestion.
* 4 Use Amazon Kinesis Data Analytics for real-time analytics.
* 5 Use AWS Glue to catalog datasets automatically.
* 6 Data transformation.
* 7 Run interactive ETL scripts in Jupyter notebooks on AWS Glue using Glue interactive sessions.
* 8 Use Glue Studio to run and monitor ETL jobs on AWS Glue.
* 9 Use Glue DataBrew for data preparation.
* 10 Use EMR to run Spark transformation jobs.
* 11 Load data into Amazon Redshift from Glue.
* 12 Introduction to Amazon Redshift best practices.
* 13 Query data with Amazon Athena and visualize with Amazon QuickSight.
* 14 Clean up resources.