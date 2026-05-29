# AWS Compute Services

## Amazon Elastic Compute Cloud

QUE: what is Amazon Elastic Compute Cloud (EC2)??
	- is an AWS service that provides resizable virtual servers in the cloud [provides resizable compute capacity in the cloud].
	- each individual EC2 machine is referred to as an instance
Key characteristics:
- ability to scale up or down based on demand.
- availability of a varied range of instance type for specialised use class

- AWS offers six EC2 instance categories of EC2 instances for specialised workloads:
	1. general purpose
	2. compute optimised
	3. memory optimized
	4. accelerating computing
	5. high-performance computing (HPC) optimised

1. General purpose and storage optimised instances
	- general purpose instances:
		- balance of compute, memory, and networking resources.
		- use cases:
			- hosting dynamic websites
			- maintaining code repositories
	- storage optimised instances
		- high, sequential read and write access to large datasets
		- use cases:
			- data warehousing
			- refactoring large relational databases
2. Compute and memory optimised instances
	- compute optimised instances:
		- compute-intensive and high-performance workloads
		- use cases:
			- scientific simulations
			- financial modelling
	- memory optimised instances
		- memory-intensive workloads not requiring high storage
		- use cases:
			- real-time stream data analytics
			- generating close captions
3. Specialised compute instances
	- accelerated computing instances:
		- contain specialised hardware accelerators, like GPUs or FPGAs
		- use cases:
			- deep learning
			- rendering gaming graphics
	- HPC optimised instances:
		- best price performances for running high performance workloads at scale
		- use cases:
			- weather forecasting
			- crash simulations

- when creating an EC2 instance, we have to configure several key components. the Amazon Machine Image (AMI) is a template that defines the software, such as the operating system, running the instance.
	- the key-pair is a security credential used to connect to the instance. the public key is stored on the instance and the private key on the local computer.
	- the Virtual Private Cloud (VPC) - is a virtual network dedicated to the AWS account, with one configured by default for each region. 
	- security group acts as a firewall, controlling inbound and outbound traffic, while FBS volume refers to the root storage of the machine image. 

Connecting to the EC2 instance: SSH Client
- connecting to the EC2 instance is crucial for managing cloud infrastructure. 
- SSH connects with a private key
	- NB: those keys must be managed

Connecting to the EC2 instance: AWS Session Manager
- AWS Session Manager offers secure, keyless access via the Management Console or CLI, eliminating the need for SSH keys or open ports. 
	- ideal for security-focused organisations as it integrates with IAM for fine-grained control and logs session activity.

Connecting to the EC2 instance: EC2 Instance Connect
- browser-based connection without needing an SSH key
- quick and temporary access


## Load Balancing and Auto-scaling

- load balancing ensures even distribution of incoming traffic among multiple EC2 instances, preventing overload on a single server.
	- ensures high availability
	- provides horizontal scaling
- types of load balancers in AWS:
	- classic load balancer
	- netwok load balancer
	- application load balancer
	- gateway load balancer

- QUE: how does load balancing work??
	- users send requests and, the requests hit the load balancer. primary target group is instantiated by the application load balancer first. if demand increases, the load balancer activates the secondary target group and distributes the load across all instances. 


- QUE: what is compute elasticity?
	- elasticity ensures the system can scale up or down based on demand, providing flexibility in resource allocation.
		- EC2 instances achieve elasticity through EC2 Auto Scaling
		- QUE: what is EC2 Auto Scaling??
			- automatically adjust the number of active instances based on usage and requirement
				- optimised costs and prevent over-provisioning.
- QUE: how does auto-scaling work??
	- users send requests. the requests are routed to EC2 Auto Scaling service, then the service routes requests to the active EC2 instances. if demand increases, it starts adding new EC2 instances to manage the additional load. as demand goes down, the newly added EC2 instances are shut down.


- QUE: what is the difference between load balancing and auto-scaling??
	- load balancing: route traffic evenly. utilises existing EC2 instances 
		- [AWS Load Balancer]()
	- auto-scaling: ensure demand is always met. ability to add/remove EC2 instances
		- [EC2 Auto Scaling]()


## Serverless Compute

- EC2 Recap:
	- Amazon EC2 is a service that provides compute capacity in the AWS cloud
	- using EC2 gives higher flexibility and control
	- variety of EC2 instance types optimised for different workloads.

- today's demands:
	- need for modular, microservices architecture. rapid scaling capabilities to meet fluctuating demands. automated infrastructure management setup without interventions
- AWS offers solutions to these problems through containers and serverless compute.

- QUE: what are containers??
	- containers encapsulate applications and their dependencies in lightweight singular units.
	- why containers?? 
		- isolate applications from underlying system dependencies
		- share host OS for efficient resource utilisation
		- easily movable and portable across environments
- AWS provides container services through Amazon ECS and EKS. both offer scalability, integrating seamlessly with other AWS services like databases and storage.
- QUE: what is the difference between ECS and EKS
	- Amazon ECS - fully managed service for efficient deployment, management, and scaling of containerised applications. 
		- use cases: deploying and managing microservices-based applications. plan, schedule, and run batch processing workloads across AWS services.
	- Amazon EKS - container orchestration service specialising in running Kubernetes-powered applications
		- use cases: pair with EC2 accelerated computing instances to run ML containers
		- manage clusters and applications in hybrid cloud environments. 

- QUE: what is serverless architecture??
	- serverless compute focuses on code and outcomes rather than infrastructure, eliminating the need to provision, scale or maintain servers [no server management].
	- event-driven: functions triggered by events in real-time
	- cost-efficient: pay only for actual usage, not pre-allocated resources
- serverless is perfect for event-driven applications, real-time file processing, and scenarios where compute needs fluctuate rapidly, like chatbots or voice assistants
- AWS offers serverless compute through:
	1. AWS Lambda - run code in response to events without provisioning or managing servers. automated compute scaling capabilities.
		- example: suppose a website can only show docs of a specified size. to achieve this we will have a Lambda function that is designed to be triggered whenever a new file is uploaded. this function runs a compression algorithm on the file to ensure that the file sizes stay in the limit that is acceptable to the website's frontend.
	2. AWS Fargate - offers a hybrid implementation that blends containers into a serverless environment, enhancing efficiency, eliminating server management, and reducing overall costs. 
		- use cases:
			- enable AI and ML applications without the need for excessive server provisioning
			- batch processing of large datasets with parallel compute capabilities