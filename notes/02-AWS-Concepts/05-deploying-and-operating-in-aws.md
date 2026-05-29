## Deploying and operating in AWS

Provisioning resources in AWS
- it is the process of allocating and configuring cloud services like servers, storage, and networking.
- two methods:
	1. one-time operations where the client manually sets up resources or uses automation for consistent, repeatable deployments.
		- AWS offers tools like CloudFormation for Infrastructure as Code (IaC) which allow clients to define their cloud environment in templates and also automate the process ensuring consistency and reduction in manual errors which is ideal for large-scale operations.
- accessing AWS services:
	- ==AWS Management Console== - web based user interface that provides a graphical way to manage and configure AWS services. suitable for those who prefer visual management.
	- ==Programmatic Access== - AWS Command Line Interface (CLI),  Software Development Kits (SDKs), and APIs
	- Infrastructure as Code - tools like AWS CloudFormation or third-party solutions like Terraform [essential for automating deployments]

Cloud deployment models
1. public cloud:
	- all resources are hosted on AWS and shared with others
	- cost efficient and scalable
2. private cloud:
	- dedicated resources to a single organisation
	- strict compliance or security
3. hybrid cloud
	- mix of on-premises and cloud services

- AWS provides several connectivity options:
	- AWS VPN - encrypted connection between your network and AWS. 
		- flexible and cost-effective for temporary connections
	- AWS Direct Connect - private network connection
		- higher bandwidth and better performance
	- Public Internet
		- resources are public facing