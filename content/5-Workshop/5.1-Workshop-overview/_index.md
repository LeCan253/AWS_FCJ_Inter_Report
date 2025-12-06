---
title : "Introduction"
date :  2025-12-01
weight : 1 
chapter : false
pre : " <b> 5.1. </b> "
---

#### About VPC Endpoint

+ VPC Endpoint is a virtual appliance in VPC, allowing internal resources (EC2, Lambda, CodeBuild, CodePipeline…) to access AWS services without going through the public Internet. This helps reduce risk, increase security and ensure high availability.

+ With Gateway Endpoint, services such as Amazon S3 can be accessed directly from VPC without going through the Internet.

+ With Interface Endpoint (AWS PrivateLink), services such as Security Hub, ECR API, SNS, or CodeGuru Reviewer can be accessed privately between services in AWS, helping DevSecOps pipelines operate securely and stably even without opening the outbound Internet.

#### Workshop Overview

+ Pipeline uses a single VPC, in which CI/CD and security services are connected internally through VPC Endpoint:
+ **Security VPC** is where the main resources of the pipeline such as CodeBuild, Lambda for analysis, gateway endpoint to access S3, and interface endpoint to connect to Security Hub, ECR, CodeGuru Reviewer, SNS, ... This VPC simulates a real cloud environment, where all scan - build - analysis activities are handled in a private network.
+ **In the pipeline, CodeBuild** will scan for vulnerabilities in images/containers using Trivy, scan Python/JS security using Bandit, analyze source code quality with SonarQube, push warning results to AWS Security Hub, send real-time warnings via SNS

![overview](/images/5-Workshop/5.1-Workshop-overview/diagram1.png)
