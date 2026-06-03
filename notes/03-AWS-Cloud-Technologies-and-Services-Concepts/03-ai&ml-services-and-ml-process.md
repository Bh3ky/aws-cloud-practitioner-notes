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
- 