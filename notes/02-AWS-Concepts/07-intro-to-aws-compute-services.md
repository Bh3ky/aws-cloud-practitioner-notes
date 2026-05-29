## Introduction to AWS Compute Services

- AWS Compute services provide the computing power needed to keep the businesss running smoothly during high-demand events.

Compute: the backbone of digital solutions
- Definition: providing computing power on demand
- Importance: scalability, flexibility, and cost-efficiency

- AWS offers two primary computing modes:
	1. server-based - has continuous availability, dedicated resources, more control, and customisation.
		- Note: ideal for applications requiring specific configurations and continuous availability.
	2. serverless - on-demand execution, no server management, event-driven, cost-effective.
- NB: understanding when to use a server-based architecture versus a serverless architecture is crucial for balancing performance, scalability, and cost-efficiency.

**AWS EC2**
- virtual servers in the cloud
- customisable configurations (OS, storage, location)
- focus on customisation
	- USE: hosting websites due to its scalability and customisation features.

**Lambda**
- it is an AWS's serverless computing platform
- designed to be event-driven, automatically running code in response to various events e.g., processing a file the moment it is uploaded or updating a database when a record is added.
- NB: it's more about convenience than customisation.
	- USE: real-time image processing. event-driven tasks. 


## Introduction to AWS Database Services

- AWS Database services ensure that the data is well-organised and accessible.
- there are two types of databases:
	1. relational databases - these are well-organised bookshelves that systematically store and manage data. 
		- AWS Relational Database Service (RDS) supports various database engines like MySQL, PostgreSQL, Oracle, and SQL Server
		- RDS is designed for applications that need structured data with clear relationships like financial systems or e-commerce platforms. 
	2. NoSQL databases - are more like dynamic magazine racks offering flexibility and speed in data management.
		- AWS DynamoDB represents this category using a key-value model that ensures fast, predictable performance even at web scale.

- AWS RDS is a fully managed service that simplifies setting up, operating, and scaling relational databases in the cloud.
	- highly scalable, cost-effective, and supports multiple database engines
	- application: for platforms like ERP systems, CRM platforms, or financial applications.
- DynamoDB is AWS's NoSQL database solution designed for large-scale, high-traffic applications.
	- offers single-digit millisecond latency, which is critical for real-time applications

- AWS offers a broad range of specialised database solutions tailored for specific needs:
	1. ElastiCache - for caching in-memory data to speed up response times
	2. Amazon Neptune - graph database service for applications navigating complex relationships like social networks.
	3. Amazon DocumentDB - document-oriented database service, which is ideal for content management and catalogs.
	4. Amazon Timestream - time-series dataabase optimised for storing and analysing time-stamped data perfect for IoT and operational applications
	5. Amazon QLDB (Quantum Ledger Database) - a ledger database for applications needing an immutable, verifiable transaction log

- AWS Database Service (DMS) allows for the migration of databases with minimal downtime supporting both homogeneous and heterogeneous migrations


## Introduction to AWS Storage Services

- focus: Amazon S3 & Amazon Glacier
- storage:
	- keep data safe and accessible, backups, and larger files, documents etc
	- disaster recovery and archiving
- databases:
	- organising and querying structured data
- AWS storage services:
	1. Amazon Simple Storage Service (S3)
		- object storage with industry leading scalability, availability, and security for storing and retrieving any amount of data from anywhere.
	2. Amazon Elastic File System (EFS)
		- a simple, serverless, elastic, set-and-forget file system for sharing data without managing storage
	3. Amazon FSx
		- fully managed, cost-effective file storage offering the capabilities and performance of popular commercial and open-source file systems.
	4. Amazon Elastic Block Store (EBS) 
		- easy to use, high-performance block storage service for both throughput and transaction-intensive workloads at any scale.
	5. Amazon File Cache
		- a high-speed cache for datasets stored anywhere accelerates cloud-bursting workloads.

- there are two types of storage:
	1. active storage (direct storage)
		- like recent emails, and it is readily accessible
		- ideal for daily operations due to its ready accessibility
		- AWS S3: designed for ease of access and management
			- object storage used for storing and retrieving any amount of data, anytime from anywhere
			- NB: can be pricey
	2. archival storage
		- like old emails, accessed infrequently
		- ideal for long-term data retention
		- AWS Glacier: cost-effective for long-term storage
			- used for data archiving and long-term backup
			- long-term, low-cost, and secure cloud storage services

**AWS S3**
- S3 stands for Simple Storage Services
- highly scalable, durable, and secure. wide variety of use cases like website hosting, data backup, and content distribution
- storage classes:
	- S3 Standard:
		- frequently accessed data
		- low latency, high throughput
		- content distribution and dynamic websites
	- S3 Intelligent-Tiering
		- moves data between frequent and infrequent access tiers
		- optimises storage costs
	- S3 Standard-IA (Infrequent Access)
		- less frequently accessed data, but still needs rapid access
		- backups and disaster recovery
	- S3 Glacier and S3 Glacier Deep Archive
		- long-term archival of rarely accessed data
