## Define the AWS Global Architecture

1. AWS Region - is an independent geographic are that consists of multiple isolated locations known as Availability Zones. 
	- regions allow for deployments of applications and services close to the customers to reduce latency and meet data sovereignty requirements. each region operates independently and is physically separated from other regions
2. Edge Locations - these are data centers located worldwide that AWS uses to cache content and provide services closer to end-users. 
	- they help reduce latency and improve the performance of applications by delivering content through services like Amazon CloundFront
	- edge locations are part of the AWS Global Network and are typically used for services that require low-latency responses such as content delivery and DNS reduction
3. Availability Zones (AZ) - are physically distinct, isolated location within an AWS Region.
	- each AZ has its own power, cooling, and networking infrastructure to ensure redundancy and high availabilty
	- AZs within a Region are connected via low-latency links, enabling the client to build fault-tolerant and highly available applications.
	- multiple AZs ensure that applications are protected against failures in a single location. 