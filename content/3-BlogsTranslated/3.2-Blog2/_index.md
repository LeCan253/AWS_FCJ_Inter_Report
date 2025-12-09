---
title: "Blog 2"
date: 2025-09-30
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---
# Real-time dashboards from source database to cloud data warehouse on AWS

**Author:** Ofir Eshel
**Date:** 27/02/2025
**Category:** Amazon Aurora • Amazon EC2 • Amazon QuickSight • Amazon Redshift • AWS DMS • IAM • Secrets Manager • Kinesis • RDS MySQL • Serverless • Technical Guide

---

## 1. Introduction

Organizations today need **real-time or near-real-time** dashboards to display data to customers without affecting production database systems. This article presents an end-to-end AWS architecture that enables change data transmission (CDC) from source database to cloud data warehouse and visualization using Amazon QuickSight, with low latency and no system performance impact.

---

## 2. Overview Architecture

The solution assumes the system has multiple offices that record visits and want to display:

- **Number of people waiting**
- **Current waiting time**
- **Dashboard embedded in website**
- **BI data mining on data warehouse**
- **No heavy load on source database**

### Main components:

- **AWS DMS** – capture change data (CDC) from RDS MySQL
- **Kinesis Data Streams** – streaming data
- **Amazon Redshift Serverless** – data warehouse analysis & storage
- **Amazon QuickSight** – real-time dashboard display

---

## 3. Prerequisites

- AWS account with access to the above services
- Basic knowledge of AWS Console
- Understanding of database, VPC, IAM

---

## 4. Configure source database (RDS MySQL)

1. Create RDS MySQL (db.t4g.micro).
2. Enable **IAM Database Authentication**.
3. Launch EC2 Windows to install **MySQL Workbench**.
4. Configure Security Group:

- EC2 → outbound 3306 → SG RDS
- RDS → inbound 3306 → SG EC2
5. Install MySQL Workbench and connect RDS using IAM.
6. Enable CDC:
- Create Parameter Group
- `binlog_format = ROW`
- `binlog_row_image = FULL`
7. Assign Parameter Group to DB and **reboot**.
8. Create schema `anycounty` and demo data table.

---

## 5. Configure Kinesis Data Streams

1. Create a new stream named: **streamforrds**
2. Select **On-demand** mode to automatically scale.

---

## 6. Configure AWS DMS for CDC

1. Create a **subnet group** for DMS.
2. Create a **Replication Instance** of type `dms.t3.micro`.
3. Create a **Secrets Manager** containing the user/password database.
4. Create a **source endpoint** (RDS MySQL).
5. Create an **IAM Role** for DMS to read Secrets Manager.
6. Create a **destination endpoint** (Kinesis).
7. Create and run a **CDC replication task** for the schema `anycounty`.
8. Check the data streaming into Kinesis Viewer.

---

## 7. Configure Amazon Redshift Serverless

1. Create an IAM Role for Redshift to read Kinesis data.

2. Create a Redshift Serverless Namespace + Workgroup.

3. Enable:
- Private connectivity
- VPC endpoint to Redshift

4. Allow IP QuickSight (`52.23.63.224/27`) to access port 5439.

### Create schema and view in Redshift

```sql
CREATE EXTERNAL SCHEMA kds
FROM KINESIS
IAM_ROLE '<role-arn>';
