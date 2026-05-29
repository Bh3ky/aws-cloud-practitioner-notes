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