# AWS Machine Learning, AI & Analytics

## AI & ML Services and Machine Learning Process

**Question: what is AI and ML??**
- artificial intelligence is essentially a way of simulating human intelligence in machines involving tasks like problem solving, speech recognition and learning. 
- machine learning is a subset of AI that focuses on systems that learn from vast amounts of data to infer results.

**Introducing AWS AI services**
- pre-trained, auto-trained models
- no machine learning background needed

1. Amazon Translate - service that can automatically translate text into multiple languages.
2. Amazon Polly - text-to-speech service that can convert input text into human-sounding speech.
3. Amazon Lex - create conversational interfaces like chatbots
4. Amazon Comprehend - extracts insights from text. identify sentiments, entities, and language.
5. Amazon Forecast - service that can automatically generate time-series predictions based on input data. 
6. Amazon CodeGuru - developer-friendly service that is used to automate code reviews. specialises in generating intelligent recommendations for improving code quality. 
7. Amazon Rekognition - object recognition service that can identify and extract information like sentiments from videos and images.


**ML services in AWS**
- enable developers to build custom ML models
- tailored for those with ML expertise and specific use cases.

1. Amazon SageMaker - fully managed service for end-to-end ML lifecycle. integrated Jupyter notebooks for model development. one-click training and deployment.
    - used for designing predictive analytics, computer vision, and natural language processing applications.

2. Amazon CodeWhisperer - ML-driven code reviewing service that enhances code quality, automates and streamlines the complete code review process.


**ML frameworks**
- open-source frameworks for diverse ML workflows. they enable robust, scalable, and seamless deployment. 

**AWS services enabling ML frameworks**

1. TensorFlow - development and deployment of scalable ML models on AWS
2. PyTorch - execute machine learning and computational graph-based systems on-the-fly.
3. MXNet - large-scale, distribtued training of deep neural networks.


**Sample ML pipeline**
- the source data that needs to be prepared will be stored in an S3 bucket. the ML model development and training will take place in SageMaker which reads data directly from S3.
- for deployment, the SageMaker notebook is packaged into a container and pushed to production through EKS.
- AWS Lambda is for re-training and deployment of the pipeline whenever new data is available.


## Analytics & BI Services

- data analytics involves collecting, processing, and transforming data to gain insights.

**Data Analytics in AWS**

1. Amazon Athena
- serverless, interactive analytics service for analyzing petabyte-scale data at source. 
- key features:
    - versatile data integration
    - simplified pricing of paying per query.

2. Amazon QuickSight
- unified business intelligence service supporting interactive dashboards.
- key features:
    - automatic scaling without server setup
    - generative BI capabilities
    - supports paginated reports for offline sharing.

3. Amazon Kinesis
- enbales the collection, processing, and analysis of data streams at scale.
- key features:
    - real-time processing
    - serverless infrastructure
    - scalability

4. Amazon Redshift
- AI-powered, Massively Parallel Processing (MPP) cloud data warehouse for analytics.
- key features:
    - achieve up to 6x better price performance
    - zero-ETL approach
    - secure collaboration and governance

5. Amazon Macie
- ML-driven data security service to enable sensitive data discovery and protection.
- key features:
    - automated discovery
    - cost-efficient visibility
    - reduce triage time with actionable reporting on sensitive data.

6. AWS Glue
- serverless data integration service allowing the discovery, preparation and integration of data.
- key features:
    - support both batch and streaming data
    - prepare data for machine learning and deep learning.
    - serverless petabyte-scale capacity.


**Creating an end-to-end data workflow**
- supports we want analyze data usage from a mobile app, we would use Amazon Kinesis to ingest real-time data coming in from the mobile app and store it in S3.
- then we write a simple function in AWS Glue to transform the data and move it to Amazon Redshift and Amazon Athena.
- Amazon Macie is setup across S3, Redshift, and Athena to monitor for any sensitive data being flown into the systems.
- QuickSight can then be used to read data from Athena and build interactive reports to present the analysis to others.


## Secondary AWS Service Categories

**Question: list the core AWS services??**
1. AWS Global infrastructure
2. Compute
3. Storage
4. Databases
5. Networking
6. Analytics & AI

**Application integration services**
- enhance communication between diverse AWS applications.
- coordinate data and workflows for efficiency.
- crucial for scalable, flexible, interconnected architectures. Example:

1. Amazon EventBridge
- key features:
    - applications that respond to real-world events at any scale
    - connect different software and systems.
- use cases:
    - build software without explicit dependencies between systems
    - monitor and audit AWS environments.

2. Amazon Simple Queue (SQS)
- messaging for software components, ensuring reliable communication at any volume
when is SQS used?
    - connect microservices for reliability and scale.
    - decouple components for increased background efficiency.

3. Amazon Simple Notification Service (SNS)
- facilitating application-to-application (A2A) and application-to-person (A2A) messaging
- use cases:
    - send push, SMS, email notifications to customers
    - integrate FIFO messaging between applications

**Business application services**
- streamline operations and enhance efficiency of business applications. 
- seamless integration, automation, and improved productivity.

1. Amazon Connect - cloud-based customer contact center offering service.
    - use cases:
        - scalable customer support
        - personalised customer interactions

2. Amazon Simple Email Service (SES)
- scalable and cost-effective email service supporting marketing and transactional communication
- how is SES used?? bulk email sending and application-generated emails.

**Developer services**
- cohesive environment for simplifying and accelerating the development lifecycle.
- enable collaborative development within teams and tools.
- automated delivery and deployment using CI/CD.

AWS CodePipeline
- automate continuous delivery pipelines and infrastructure updates.
- use cases:
    - updating existing pipelines or create new ones with JSON templates.
    - real-time notifications on pipeline-affecting events.

AWS CodeCommit
- host private Git repositories with fully managed, scalable source control service
- when to use CC??
    - facilitate code collaboration with built-in code reviews
    - seamlessly use existing tools, plugins, CI/CD systems, and graphical clients.


**Advanced intelligence service**

1. AWS IoT Core
- secure connections for IoT devices to the cloud, enabling easy device management and scalability.
- use cases:
    - develop industrial IoT applications for predictive maintainance and quality monitoring
    - build connected solutions for home automation. 

2. Amazon Braket
- facilitate quantum computing research with tools, access, and support.
- what does Bracket do?
    - gives tools for developing quantum algorithms
    - enables testing and exploration of various quantum hardware
