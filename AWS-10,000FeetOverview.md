Storage
  - S3
    - Object based storage called buckets.
  - EFS
    - Network attached storage
  - Glacier
    - For Data Archival for very cheap.
  - Snowball
    - Bring large amounts of data to Amazon data center.
  - Storage Gateway
    - Virtual machines you install in your data center. Will replicate information to S3. There are 3 Types

Databases
  - RDS
    - MySQL, PostSQL, Auora (Amazon version)
  - DynamoDB
    - non-relational database
  - Elasticache
    - Caching service
  - Red Shift
    - Data warebousing or business intelligence. For complex queries.

Migration
  - AWS Migration Hub
    - Tracking service when migrating service to AWS
  - Application Discovery Service
    - Automated. Detect applications and dependencies
  - Database Migration Service
    - Easy way to migrate data from on premise to AWS
  - Server Migration Service
    - Similar to Database Migration Service
  - Snowball
  
Networking and Content Delivery
  - VPC
    - Virtual Data Center. Configure network related stuff.
  - CloudFront
    - CDN for Amazon. Using edge locations
  - Route53
    - DNS service. Looking for IP Addresses and who it belongs to
  - API Gataeway
    - Creating your own API for you services to talk to
  - Direct Connect
    - Way of running dedicated line to your VPC

Developer Tools
  - CodeStar
    - Way of project managing code with developers
  - CodeCommit
    - Code storage. Source control service. Git repository.
  - CodeBuild
    - Will compile code and run test. Create software packages that will be ready to deploy
  - CodeDeploy
    - Automates application deployments to EC2 instance, on-premise instance, or lamda functions
  - CodePipeline
    - Continous delivery service used to model and visualize and automate steps to release your software
  - X-Ray
    - Used to debug and analyze serverless applications. Has request tracings.
  - Cloud9
    - IDE environment to develop code inside AWS console.
  
Management Tools
  - CloudWatch
    - Monitoring service
  - CloudFormation
    - Way of scripting infrastructure
  - CloudTrail
    - Log changes to AWS environment. Turned on by default and stores for a week.
  - Config
    - Monitors config of all AWS environments. Point in time snapshots.
  - OpsWorks
    - Automating your config for your environments
  - Service Catalog
    - Managing catalogs.
  - Systems Manager
    - Managing AWS resources. Used for EC2 such as security patches. Can group resources
  - Trusted Advisor
    - Give you advice around security, AWS utilization, etc.
  - Managed Services
    - Manages your AWS cloud

Media Services
  - Elastic Transcoder
    - Makes media work well for whatever platform it is viewed on
  - MediaConvert
    - File based media transcoding service
  - MediaLive
    - Broadcast live processing service. High quality video streams.
  - MediaPackage
    - Prepares and protects media to be delivered over internet
  - MediaStore
    - Store service optimized for media. Used to deliver live, on-demand content.
  - MediaTailor
    - Allows you to do targeted advertisement
  
Machine Learning
  - SageMaker
    - Makes it easy for developers to use deep learning
  - Comprehend
    - Sentiment analysis for data
  - DeepLens
    - Artifically aware camera. Physical hardware you can buy
  - Lex
    - Way of communicating with customers
  - Machine Learning
    - Analyze datasets
  - Polly
    - Takes text and turns it into speech.
  - Rekognition
    - Recognizes stuff in pictures/videos
  - Amazon Translate
    - Machine translation service
  - Amazon Transcribe
    - Automatic speech recognition

Analytics
  - Athena
    - Allows you to run SQL queries in your S3 bucket
  - EMR
    - Processing large amount of data. Chops data for analysis
  - CloudSearch
    - Search service for AWS
  - ElasticSearch Service
    - Search service for AWS
  - Kinesis
    - Way of injesting large amounts of data into AWS
  - Kinesis Video Streams
    - Way of injesting large amount of video stream and process them
  - QuickSight
    - Business intelligent tool
  - Data Pipeline
    - Moving data between different AWS services
  - Glue
    - For Extract, Transform, and Load. 

Security & Identity & Compliance
  - IAM
    - Role manager
  - Cognito
    - Temporary device authentication for mobile devices to use AWS resources
  - GuardDuty
    - Monitors for malicious activities on AWS account
  - Inspector
    - Install on VM and you can run whole bunch of test against it. Check security vulnerabilities for resources and generates a report.
  - Macie
    - Scan S3 bucket for personal identifiable informations
  - Certificate Manager
    - SSL certificate management
  - CloudHSM
    - Dedicated bits of hardware to store your keys. Uses these keys to access EC2 instances. Hardware security modules.
  - Directory Service
    - Integrating microsoft direct services with AWS services
  - WAF
    - Layer firewall for application layer. Ex: cross site scripting, sql injections
  - Shield
    - DDOS mitigation
  - Artifact
    - Audit and compliance. Way of inspecting Amazon's documentations

Mobile Services
  - Mobile Hub
    - Management console
  - Pinpoint
    - Target push notifications
  - AWS AppSync
    - Upstate web and mobile applications in realtime
  - Device Farm
    - Test apps on real live apps
  - Mobile Analytics
    - Analytics for mobile

AR/VR
  - Sumerian
    - Used for AR, VR, and 3D application. Don't need to understand how to code.
  
Application Integration
  - Step Functions
    - Manage different lamda functions and steps to go through it
  - Amazon MQ
    - Message queues
  - SNS
    - Notification service
  - SQS
    - Way of decoupling your infrastructure using a queue
  - SWF

Customer Engagement
  - Connect
  - Simple Email Service
    - Send large amount of email

Business Productivity
  - Alexa for Business
  - Chime
    - video conferencing
  - Work Docs
    - dropbox for AWS
  - WorkMail
    - email through amazon

Desktop & App Streaming
  - Workspaces
    - VDI solutions. OS is running in cloud and streamed to your device
  - AppStream 2.0
    - Streaming application from the cloud to your device

Internet of Things
  - iOT
  - iOT Device Management
  - Amazon FreeRTOS
  - Greengrass

Game Development
  - GameLift
    - Help develop games in AWS cloud

SA Associate Exam Material
  - AWS Global Infrastructure
  - Compute
  - Storage
  - Databases
  - Migration
  - Networking & Content Delivery (in-depth: VPC)
  - Management Tools
  - Analytics
  - Security & Identity & Compliance
  - Application Integration
  - Desktop & App Streaming

Developer Associate Exam Material
  - AWS Global Infrastructure
  - Compute
  - Storage (in-depth: S3)
  - Databases (in-depth: DynamoDB)
  - Networking & Content Delivery (in-depth: VPC)
  - Management Tools
  - Analytics (in-depth)
  - Security & Identity & Compliance
  - Application Integration (in-depth)

Sysops Administrator Associate Exam Material
  - AWS Global Infrastructure (in-depth)
  - Compute
  - Storage (in-depth)
  - Databases
  - Networking & Content Delivery (in-depth: VPC)
  - Management Tools (in-depth: CloudWatch, CloudTrail)
  - Security & Identity & Compliance (in-depth)
  - Application Integration (in-depth)