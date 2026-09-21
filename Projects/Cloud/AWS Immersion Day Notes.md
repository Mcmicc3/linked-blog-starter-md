August 10th 2026

# The Big Picture

240+ Services
Grouped into four.

##### ***Compute  |   Storage  |  Database  | Networking***

**Compute**: Runs apps & Workloads
* *AWS Services*: C2 ~ Lambda ~ Containers
  
**Storage**: Store files & data
* *AWS Services*: S3 ~ EBS ~ EFS 
  
**Database**: Managed data stores
* *AWS Services*: RDS ~ DynamoDB
  
**Networking**: Connect & Secure
* *AWS Services*: VPC ~ Route 53 ~ Cloudfront


## Storage: Three Types

**Amazon S3**
*Object storage*
Store any amount of files as obkects in buckets. DUrable (11 nines), cheap, calable/ FOr backups, ,edia data, sakes, static websites

**Amazon EBS**
*Block Storage*
Virtual hard drives attached to EC2 instances. Persisstent, high performance. This is the volume your EC2 lab instance boots from.

**Amazon EFS**
*File Storage*
Shared file systtem many instances mount at once. Grows automatically. For shared content, lift and shift file workloads.

## Databases: Managed for you
AWS runs the datbase engine, patching, backups & scaling - you focus on your data.

**Amazon RDS**
*Relational (SQL)*
* Managed relational databases
* ENgines: PostgresSQL, MySQL, MariaDB, SQL Server, Oracle
* Structured data & Fixed Schema
* Automated backups & fail over
* For traditional apps, transactions.

**Amazon DynamoDB**
*NoSQL (key-value)*
* Fully managed NoSQL database
* Single-digit millisecond latency
* Flexible schema, massive scale
* Serverless - no servers to manage
* For high-traffic web & mobile apps.

## The well-architected Framework
AWS's guidelines for building good cloud systems - six pillars to design against

1. **Operational Excellence**
	* Run & monitor systems, continuously improve
2. **Security**
	* Protect data, systems & assets
3. **Reliability**
	* Recover from failure, scale to meet demand
4. **Performance Efficiency**
	* Use resources efficiently as needs change
5. **Cost Optimization**
	* Avoid unnecessary cost, pay for what you use
6. **Sustainability**
	* Minimize environmental impact of workloads.

## How it all fits together
Every application you build combines these building blocks inside a secure network

***Networking (VPC) + Compute (EC2) + Storage (S3/EBS) + Database (RDS) + Security (IAM)***


## Introduction to Amazon Cloud & Networking Overview

## AWS Shared Responsibility Model


## How to interact with AWS

1. **AWS Console**
	* Web-based GUI. Point and click
2. **AWS CLI**
	* Command line tool. Script & automate the same actions
3. **AWS CDK**
	* Define infrastructure as code

## AWS Cloud Development Kit (CDK)
Fine your cloud infrastructure using a real programming language

## Global Infrastructure
AWS Region is compromised of multiple AZs for high availability , in scalability, and high fault tolerance. Applications and data can be icated in real time with consistency across different AZs.

## AWS Availability Zone (AZ) design
* Fully isolated infrsutructre with one or more datacenters
* Up to 60 miles apart
* Unique power infrastructure
* Many 100Ks of servers at scale
* Datacenters connected via fully redundant and isolated metro fiber
* HIgh-throughput, low latency

## VPC - Virtual Private Cloud
Provision a logically isolated section of the AWS cloud where you can branch AWS resources in a virtual network that you can define

*Bring your own network*: Addresses - subnets - Network Topology - Routing rules - Security Rules

## Elastic IP Address
Static, Public IPv4 address, associated with you AWS account in specific region............


## Security Groups
Actual firewall at the instance level
* Attached to an instances Network interface (ENI); An instance can have several
Stateful -- return traffic is automatically allowed, regardless of inbound / outbound rules
* Allow rules only -- you cannot create explicit deny rules
* Rules specify protocol, port range, 

## Network ACLs vs Security Groups

**Netowrk ACLs**
* Firewall at the subnet boundary
* Applies to all traffic entering/leaving the subnet
* Stateless -- return traffic must be explicitly allowed by a rule
* Supports both allow AND deny rules
* Rules evaluated in numbered order (lowest first)
* Default NACL allows all traffic...

**Quick Comparison**
* ...

https://catalog.us-east-1.prod.workshops.aws/join?access-code=0b0d=033252-f1
0b0d-033252-f1


---
Part 2

## What is Amazon EC2?

Amazon Elastic Compute Cloud (EC2) provides rezi....

## The AWS Compute Portfolio
Three ways to run workloads -- from full control to fully managed

***EC2  |  Containers  |  Serverless***

**EC2**: Virtual Servers
* Full control over OS, networking & configuration.
**Containers**: ECS & EKS
* Package apps in containers. Run at scale with orchestration
**Serverless**: AWS Lambda
* Just run code. No servers to manage pay per request

## EC2 Instance Families
**General Purpose**: *M, T*
* Balanced compute & memory. Web Servers, Dev environments
**Compute Optimized**: *C*
* High-performance processors. Batch processing, gaming, HPC
**Memory Optimized**: *R, X*
* Large datasets in memory. Databases, in memory caching
**Storage Optimized**: *I, D*
* HIgh sequential read/write
**Accelerated Computing**: *P, G*
* Machine learning

## AWS Graviton Processors
AWS-designed Arm-based chips --better price-perforamnce & efficiency

Up to 40% better price-performance --vs. comparable x86
Up to .....


## Choosing the right instance
What is your bottleneck?
**CPU?**
* c,,,,,,,,,
* ,,,
* ,

## EC2 Pricing Models
**On Demand**  - Full price
* Pay per second, no commitment. Best for unpredictable workloads
**Reserved**  - Up to 72% off
* 1-3 year commitment. Best for steady-state workloads
**Spot**  - Up to 90% off
* Spare capacity, can be interrupted. Best for fault-tolerant tasks.
**Savings Plans**  - Up to 72% off
* Flexible $/hour commitment. Applies across instance families.

## Amazon Machine Images (AMIs)
hAMI is a template with the OS, configuration & software to launch an instance

**Quick Start** 
AWS-provided base images -- Amazon Linux, Ubuntu, Windows, MacOS. Verified & patched.

**AWS Marketplace**
Commercial images from vetted software vendors -- pre-licensed & prodiction-ready (e.g., firewalls, databases).

**My AMIs**
Images you create from your own configured instances. Bake in your software for fast, consistent launches.

**Community AMIs**
Images shared publicly by the AWS community. Free to use -- verify the source before trusting.


## Launching an EC2 Instance

1. **Choose AMI**
   OS template (Amazon Linux, Ubuntu, Windows)
   
2. **Select Type**
	Hardware Config (t2.micro for this lab)

3. **Security Group**
	Firewall rules (allow SSH on port 22)

4. **Key Pair**
	For seucre SSH access (download.pem)

5. **Launch!**
	Instance starts in ~30 seconds & get public IP

## Launching EC2 at Scale
Beyond a single instance  - repeatable launches that grow with demand.

**Launch Templates**  - Save a resuable config  - AMI, instance type, key pair, security groups. Versioned ($Default/(Dollar_Sign)Latest) for consistent, repeatable launches 

**Instance Count & Placement**  - Launch many instances at once. Placement groups control how they're spread across hardware - cluster (low latency), spread (fault isolation), or partition.

**EC2 Auto Scaling**  - Auto scaling groups add or remove instances to match demand. Health checks replace unhealthy instances; capacity is balanced across AZs. 

**Elastic Load Balancing**  - Distributes incoming traffic across healthy instances. Pairs with Auto Scaling so your app stays available as the fleet grows and shrinks.


---

## Special Types of IAM Roles
**IAM Service Role**

**IAM Service Linked Role**


---

