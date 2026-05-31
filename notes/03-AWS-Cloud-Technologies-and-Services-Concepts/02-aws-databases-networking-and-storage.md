# AWS Database, Networking, and Storage

## Exploring AWS Database 

- AWS provides various databases for different use cases, including relational databases, NoSQL databases, memory-based databases, and compute-hosted databases.

- QUE: what are relational databases??
	- relational databases structure data into tables and build relationships to other tables using keys.
		- they provide data integrity, consistency, and scalability.
- AWS supports relational database management through two services:
	1. Amazon RDS - offers a fully managed relational database service by controlling setup, operation, and scaling. 
		- supports various database engines and scales seamlessly in both cloud and on-premises environments.
	2. Amazon Aurora - specialised database service for MySQL and PostgreSQL. offers high performance at a fraction of on-premises costs. 
		- performs continuous backups and multi-region deployments to ensure high availability.

- NoSQL databases in AWS accommodate diverse data models beyond traditional relational databases, such as JSON and raw documents
	- key features: 
		- schema flexibility - to deal with evolving data structures
		- horizontal scalability - to handle growing data.
- NoSQL database offerings:
	1. DynamoDB - managed NoSQL database built on a serverless architecture that provides high performance with limitless throughput and storage
		- 99.999% global availability and serverless capabilities for seamless scaling.
		- based used for unstructured data like real-time video streaming or media content. also used for tracking inventory or shopping carts based on customer profiles and game platform with player data, session history, and leaderboards
	2. DocumentDB - fully managed native JSON document database with MongoDB compatibility. can be used for large-scale document workloads
		- fast, reliable access to content in CMS like reviews and images
		- generate customer recommendations and manage millions of user profiles
		- unlock GenAI use cases such as semantic search, product recommendations, and chatbots

- memory-based databases - designed for high-performance data storage and retrieval, utilising RAM for faster access.
	- optimal use cases:
		- caching frequently accessed data
		- real-time analytics and data processing
		- high-speed transactional applications

- MemoryDB for Redis - AWS's offering for memory-based databases that gives microsecond read and millisecond write capabilities
	- key features:
		- super-fast read and write capabilities
		- 99.99% availability
		- near instantaneous recovery without any data loss

- QUE: what are EC2-hosted databases??
	- [also known as compute-hosted databases] these are custom database deployed on EC2 instances to simplify data access during compute.
	- they provide granular configuration and management, while leaving the responsibility of backups with the user. 

	Compute database vs static database
	- compute database heavily relies upon in cloud-native environments, where storage is separated from computing power.
	- static database (or static reference tables) stores data that serves as a permanent baseline for applications.


## Database Migration Services in AWS

- QUE: what is database migration??
	- database migration is the process of moving all of the data from one environment to a brand new environment. 


- the reason why need data migration is because legacy systems are unable to meet the rapidly changing scalability and efficiency demands.
	- generative AI has advanced systemic needs for compute and storage.
	- also need for unified data management for a diverse sources.

**Data migration in practice

1. Assessment - assessing existing data structures, formats, and dependencies of the source data.
2. Preparation - develop a clear migration plan and organise the source data
3. Execution - necessary tools and operations will be deployed to perform database migration without inconsistencies
4. Validation - verifying data integrity post-migration and conduct thorough testing
5. Optimisation - fine-tune the performance of applications in the new environment.

- AWS offers four services to support database migration:
	1. AWS Database Migration Service - facilitates the migration of databases and analytics engines to AWS
		- replicates into multiple availability zones, ensuring near-zero downtime, and supports a diverse range of source and target databases.
		- performs validation checks and task monitoring to ensure data integrity during and post-migration
			- IDEAL: large-scale, complex data migration projects across heterogeneous databases
	2. AWS Snow Family - collection of devices that facilitate the offline migration of petabyte-scale data. 
		- process data at edge locations or remote sites that are physically closer to where the source data is stored. 
		- implement robust security measures like encyption and tamper-evident seals to ensure data integrity.
			- IDEAL: effective for scenarios with large physical data volumes, restricted bandwidth, or where data must be processed at the edge before moving to AWS
	3. AWS DataSync - specialises in transferring large amounts of data from on-premises storage to the cloud.
		- has processing capabilities which ensure fast and efficient data transfer and it provides seamless integration with S3 and other data storage services.
		- also supports automation through AWS management console and internal AWS APIs
			- IDEAL: for scenarios requiring frequent and automated large-scale data transfers between on-premises storage and AWS
	4. AWS Schema Conversion Tool - automates database schema conversion by mapping source objects to corresponding target objects, minimising manual effort. 
		- allows conversion rule customisations, validates the converted schema before performing the migration, and offers live diagnostics and recommendations to address potential issues during migration.
			- IDEAL: useful for migration projects where the source and target databases have different structures, enabling a seamless transition with reduced manual intervention. 


## Network Services

- AWS networking services enable secure communicaation and content delivery between users and the cloud through:
	1. Amazon VPC - establishes networking in AWS by providing a private, logically isolated space in the global AWS infrastructure for defining and launching resources.
		- VPCs are regionally hosted, residing in one AWS region.
		- Amazon VPC provides a dedicated network supporting IPv4, IPv6 and customisable IP ranges.
		- security layers: security groups and network access control lists (ACLs).
		- complete control: subnets, route tables and network gateways.

**Question: what are IP addresses??**
- IP addresses are virtual address spaces on the network. 
- VPCs let's us define these IP addresses.
- subnets, or sub-networks are smaller VPC portions


**Question: what are route tables??**
- route tables determine where network traffic from subnet or gateway is directed


**Question: what is a network gateway??**
- connects VPC to the internet or other VPCs and controls inbound and outbound traffic.


**Default vs. custom Amazon VPC**

- default Amazon VPCs are auto-created with pre-configured settings for every AWS account. they host a susbnet in each availability zone of the region where the AWS account exists, and can communicate with the internet by default.

- while custom VPCs are user-defined with customizable features like IP addresses and route tables, and require explicit settings to allow internet access. 


**Network Security**
- AWS offers two services controlling inbound and outbound traffic to VPCs for secure connections.
- **network access control lists** (ALC) operate as a virtual firewall at the subnet level, while **network security groups** (NSGs) perform the saem operations directly for AWS services.

**VPC endpoints** - enable private connections between AWS services. they enhance security by allowing communication between services without public IP addresses. 


**Question: what is AWS PrivateLink??**
- private connectivity between VPCs, supported AWS services, and on-premises networks
- this enhances secure data exchange and reduces network and firewall complexities.


	2. Amazon VPN

- securely connects on-premises network to AWS over the internet.
- flexible and accessible, suitable for smaller workloads or temporary connections.


	3. AWS Direct Connect

- offers dedicated, highly secure, and internet-free network connections for consistent, high-bandwidth workloads.

**DNS - Internet's address book**

Domain Name System (DNS) acts as the internet's address book, translating user-friendly domain names to IP addresses for website access.


	4. Amazon Route 53

- manages domain names and translate them to IP addresses. 
- integrations with AWS ecosystem and external services. scalable and highly available.


**Content Delivery Networks (CDNs)
- distributed network of servers strategically placed globally.

Key characteristics:
- caching for faster content loading
- delivering digital content to end-users over the internet
- efficiently handle increased user traffic and demand.


	5. Amazon CloudFront

- enhances the speed and security of content delivery to end-users in AWS.
- integrates seamlessly with AWS services
- accelerates web content, APIs, and streaming.
- enhances security with DDoS protection and HTTPs support

- CloudFront accelerates website content for improved user experience, optimises streaming for reduced buffering times, and scales automatically ro deliver patches and over-the-air updates to devices


## Mastering AWS Storage Solutions

- AWS provides a diverse range of storage services tailored to meet various needs
- crucial for securely managing, storing, and retrieving data in the cloud.

**Storage types in AWS**

1. Object storage
- storage architecture that manages and organises data as discrete units called "objects".
- key characteristics:
	- horizontal scaling
	- metadata management
	- storing unstructured data like large media files, data backups, and data for complex web applications

- Amazon S3  is a highly scalable and durable object storage service offered by AWS. it is designed for 99.999999999% durability and available in all AWS regions. 

- S3 storage offers 6 classes based on latency and data requirements:
	- S3 standard is most usee storage class that is suitable for data that needs to be accessed frequently
	- intelligent tiering optimises costs by moving objects between tiers based on data access patterns
	- one zone-infrequent access operates in a single availability zone and is effective for data not requiring redundancy.
	- glacier is a low-cost option for infrequently accessed data that can withstand retrieval times of up to a few hours.
	- glacier deep archive is the most economical storage and has the longest retrieval time & is most suitable for infrequently accessed data backups.
	- S3 outposts extend storage to on-premises data, enabling a hybrid architecture for seamless on-premises and cloud data integration. 

2. Block Storage

**Question: what is block storage??**
- block storage divides data into fixed-sized blocks, each with a unique address.
- use cases:
	- running I/O intensive transaction web applications
	- right-size big data analytics engines

**Amazon EBS** - scalable, high-performance block storage service designed for use with Amazon compute services.
- comes in HDD and SSD formats, attaches directly to compute services for localised storage, ensuring 99.999% application availability.


3. File Storage

- file-based storage organises data hierarchically in directories and subdirectories, offering concurrent read-write access to multiple users and applications.
- stores metadata about files.


**Amazon EFS** - file storage service designed for use with AWS cloud services and on-premises resources.
- use cases:
	- simplify DevOps
	- enhance content management systems
	- accelerate data science

3. Cache Storage

**Cache storage services in AWS**
- stores frequently accessed data in a quickly retrievable location, speeding up application response time and reducing server load by minimising data retrieval from the original source.

Amazon ElastiCache - caching service that enables seamless, high-speed access to frequently used data.
- use cases:
	- store web application session data in-memory
	- accelerates access to real-time analytics data


**Storage lifecycle policies**
- defines the transition of objects between storage classes in S3, based on predefined rules.
- focus on cost and performance optimisation. and also improving data management and compliance.

**AWS Backup**
- cost-effective fully managed service that centralises and automates backup across AWS services.