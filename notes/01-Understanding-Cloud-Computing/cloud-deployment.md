## Cloud Deployment

**Cloud Deployment Models**

- it is the important decision in cloud adoption and is informed by how much control the client needs over their cloud environment
- three main types: private, public, and hybrid
	1. private cloud - is cloud infrastructure which is designated for exclusive use by its tenants.
		- private clouds are accessed by a network link
			- pros: direct control of resources and data
			- cons: more upfront investment [in terms of time and capital expenditure compared to other models]. 
		- the infrastructure in this model adheres to cloud principles i.e., it uses virtualisation that allows on-demand compute resources.
		- private cloud is located off-premises
	2. public cloud - cloud infrastructure is shared and open for use by the general public. it is owned and managed by a cloud service provider like AWS or Azure
		- public clouds are internet accessible
			- pros: get started quickly with minimal investment, easier to scale
			- cons: no access to data center and hardware
		- public cloud providers keep their data center locations secret, even to their clients for security reasons.
	3. hybrid cloud - is when an organisation uses a combination of two or more distinct models. the different models interact with each other via a network link and can share data and services.
		- use cases:
			- store sensitive data on the private cloud and use application on public cloud for analytics
			- cloud bursting - when private cloud hits capacity, temporarily move overflow to the public cloud to avoid disruption of service e.g., periodic spike like Black Friday sales
- other deployment models: 
	- multicloud - combines different cloud provider services for example an organisation can use Azure for backups, AWS for website hosting, and Google Cloud for analytics.
		- cons: flexibility on pricing plans and service offerings. no reliance on one vendor
	- community - infrastructure is shared by a specific community for exclusive use. common interest or concern e.g., security, jurisdiction, mission etc
		- infrastructure can be managed and hosted internally or externally.



**Regulations on the cloud**

- having servers spread out across the globe reduces latency
	- the greater the distance between two points, the longer it will take for data to get there.
	- **QUE: what is latency??**
		  it is the delay between the moment data is transmitted and the moment it is received.
- [General Data Protection Regulation (GDPR)](https://gdpr-info.eu/)
	- basically regulates how personal data is collected, processed, and stored from users in the EU.
	- examples:
		- users must explicitly consent to data collection
		- notify users of any data breaches
		- personal data information must be encrypted, anonymised, and/or pseudonymised
		- Note: personal data cannot leave EU borders, unless there is a guarantee of the same level of protection.
- **QUE: what is personal data??**
	- the European Commission defines it as any information that relates to an identified or identifiable living individual. different pieces of information which collected together can lead to the identification of a particular person, also constitute personal data. 
		- includes: _home address, first name, last name, email address, location data, IP address, racial or ethnic origin, political opinions, sexual orientation, health related data_. 
		- personal data is often referred to as PII [personally identifiable information]
- other regulations: 
	- Brazil's Lei Geral de Protecao de Dedos (LGPD)
	- California's Consumer Privacy Act (CCPA)
	- USA's Health Insurance Portability and Accountability Act (HIPAA)
	- Japan's Act on Protection of Personal Information


**Cloud computing roles**

- familiar data roles can benefit from cloud computing roles for example:
	- data scientist - run computationally expensive analyses on the cloud
	- ML scientist - train and deploy ML models on the cloud
	- data engineer - build pipelines on the cloud to ingest, transform, and store big data.
	- data analyst - access data on the cloud via business intelligence tools
- creation of new cloud roles:
	1. Cloud architect
		- solutions architect for the cloud
		- design cloud infrastructure for a given business problem
		- plan the deployment of the infrastructure
		- ensure scalability and optimise for cost
	2. Cloud engineer
		- build, maintain and monitor cloud services
		- migrating operations to the cloud
	3. DevOps engineer
		- software development + IT operations
		- infrastructure as code
		- ensure the reliability, availability, and scalability of the cloud through software development and automation.
	4. Security engineer
		- spec security requirements
		- test and assess the security of data on the cloud
		- responsible for protecting the organisation and user data from a technical perspective.

