---
title: "Worklog Week 5"
date: 2025-10-06
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---


### Week 5 Objectives:

* To help manage virtual machines, volumes and other EC2 resources, Lab 27 will practice assigning metadata to each resource as Tags and using Resource Groups.
* IAM least privilege
* IAM policy specification with conditions
* Learn about IAM Permission Boundaries.
* Learn about AWS Key Management Service (KMS), Amazon S3, AWS CloudTrail, AWS Athena.
* Review IAM concepts, create Users/Groups, Roles.
* Grant application access so it can access AWS services.
* Module 05
* Module 06

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                 | Start Date | End Date   | Resources                                                                 |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | ---------- | ------------------------------------------------------------------------- |
| 2   | **Task**: Watch and practice Module 05 - Lab 27 and Lab 28 on AWS Study Group YouTube <br> **Practice:** <br>&emsp; + Module05-LAB 27: Manage resources using Tags and Resource Groups <br>&emsp; + Module05-LAB 28: Manage access to EC2 resources using Resource Tags with AWS IAM. | 06/10/2025 | 06/10/2025 | <https://000027.awsstudygroup.com/vi/0-intro/> <https://000028.awsstudygroup.com/vi/0-intro/> |
| 3   | **Task**: Watch and practice Module 05 - Lab 30 and Lab 33 on AWS Study Group YouTube <br> **Practice:** <br>&emsp; + Module05-LAB 30: LIMIT USER PERMISSIONS WITH IAM PERMISSION BOUNDARY <br>&emsp; + Module05-LAB 33: <br>&emsp; + AWS Key Management Service (KMS) <br>&emsp; + Amazon S3 <br>&emsp; + AWS CloudTrail <br>&emsp; + AWS Athena | 07/10/2025 | 07/10/2025 | <https://000033.awsstudygroup.com/vi/1-introduce/> <https://000030.awsstudygroup.com/vi/1-introduce/> |
| 4   | **Task**: Watch and practice Module 05 - Lab 44 and Lab 48 on AWS Study Group YouTube <br> **Practice:** <br>&emsp; + Module05-LAB 44: IAM (User/Group, Role) <br>&emsp; + Module05-LAB 48: Grant application access to AWS services using IAM Role | 08/10/2025 | 08/10/2025 | <https://000044.awsstudygroup.com/vi/1-iam-intro/> <https://000048.awsstudygroup.com/vi/> |
| 5   | **Task**: Watch and practice Module 06 - Lab 05 on AWS Study Group YouTube <br> **Practice:** <br>&emsp; Theory: <br>&emsp; + Database Concepts <br>&emsp; + Amazon RDS <br>&emsp; + Amazon Aurora <br>&emsp; + Amazon ElastiCache <br>&emsp; + Amazon Redshift | 09/10/2025 | 09/10/2025 | <https://www.youtube.com/watch?v=OOD2RwWuLRw&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=217> |
| 6   | **Task**: Watch and practice Module 06 - Lab 05 on AWS Study Group YouTube <br> **Practice:** <br>&emsp; + Module06-LAB 05: Amazon Relational Database Service (Amazon RDS) | 10/10/2025 | 10/10/2025 | <https://000005.awsstudygroup.com/vi/> |


### Week 5 Results:

* Assigned metadata to each resource as Tags and used Resource Groups.
* Managed access to EC2 services using Resource Tags through detailed policy and IAM role configurations with specific permissions. Using Resource Tags is especially useful when scaling decentralized administration.

* Deployed the FCJ Management application with an Auto Scaling Group
  * Fully configured network infrastructure, launched EC2 instances and a Database Instance (Amazon RDS), deployed data and the web application.
  * Successfully configured a Load Balancer + Target Group to distribute traffic among instances.
  * Created and tested an Auto Scaling Group; the system can scale out and in automatically based on actual load.
  * Tested and evaluated scaling solutions to ensure the application runs stably and flexibly.

Why use IAM Permission Boundaries?
+ Typically, when you grant permissions to IAM users, you might think carefully crafting user policies is enough and skip using Permission Boundaries.

+ However, as the number of users grows and continuous changes in job roles require creating many new policies, permission management becomes complex and can introduce gaps that allow privilege escalation among users.

To simplify permission management, instead of editing each permission policy, you can apply Permission Boundaries quickly and consistently to help close privilege escalation gaps.

Applications of IAM

  + IAM cannot perform authentication for applications. For example, on-premises applications using AD for authentication will need AWS Directory Service (setup & migration) when moved to AWS.

  + IAM does not manage OS-level authentication. After on-premises servers are migrated to EC2, access to EC2 can be through AD or LDAP extended from on-premises or run standalone.

  + Authentication technologies:
    - AWS Management Console
    - CLI — scripting tools
    - AWS SDKs

  + Common IAM operations: Create User, Group, Role, Access Policy

Granting application access to AWS services with an IAM Role
* How to grant application access via access key / secret access key and why it is not recommended.
* How to grant application access using an IAM Role on EC2.
