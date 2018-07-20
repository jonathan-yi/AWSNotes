# S3

- S3 is a safe place to store your files
- It is Object-based storage (pictures, wordfiles, pdf, videos)
- Data is spread across multiple devices and facilities
- Files can be from 0 Bytes to 5 TB
- Unlimited storage
- Files are stored in Buckets (folder inside the cloud)
- Is a universal namespace. Names must be unique globally
- When you upload a file to S3 you will recieve a HTTP 200 code if upload was successful

### Data Consistency Model for S3
- Read after write consistency for PUTS of new objects. 
- Eventual Consistency for overwrite PUTS and DELETES (can take some times to propagate)

- Object based. Objects consist of the following:
  - Key (Simple the name of the object)
  - Value (The data and is made up of a sequence of bytes)
  - Version ID (important for versioning)
  - Metadata (Data about data you are storing)
  - Subresources:
    - Access Control Lists
    - Torrent

- Built for 99.99% availability for the S3 platform
- Amazon Guarantee 99.9% availability
- Amazon guarantees 99.999999999% durability for S3 information. 11 x 9s
- Tiered Storage Available
- Lifecycle Management
- Versioning
- Encryption
- Secure your data using Access Control Lists (individual files) and Bucket Policies (bucket level)

### Storage Tiers/Classes
-  S3 Standard: 99.99% availability, 11 x 9s durabiity, stored redundantly across multiple devices in multiple facilities, and is designed to sustain the loss of 2 facilities concurrently
- S3 - IA: (Infrequently Accessed): for data that is accessed less frequently. but requires rapid access when needed. Lower fee than S3, but charged a retrieval fee.
- S3 One Zone - IA: lower-cost option for infrequently accessed data, but do not require the multiple AZ data resilience. Only in one AZ.
- Glacier: very cheap, but used for archival. Expedidited, Standard or Bulk. A Standard retrieval time takes 3-5 hours.
- S3 Standard has no retrieval fee

- Charges
  - Charged for: 
    - Storage
    - Requests
    - Storage Management Pricing
    - Data Transfer Pricing
    - Transfer Acceleration - enables fast, easy, and secure transfers of files over long distances between your end users and an S3 bucket. Takes advantage of Amazon CloudFront's globally distributed edge locations. As data arrives at an edge location, data is routed to Amazon S3 over an optimized network path.

### Exam Tips
- S3 is object-based
- Files can be from 0 Bytes to 5 TB.
- There is unlimited storage.
- Files are stored in Buckets
- S3 is a universally namespace. Must be unique globally. Ex: https://s3-eu-west-1.amazonaws.com/{{name_of_bucket}}
- Read after Write consistency for PUTS of new Objects
- Eventual Consistency for overwrite PUTS and DELETES (can take some time to propagate)
- S3 Storage Classes/Tiers:
  - S3 (durable, immediately available, frequently accessed)
  - S3 - IA (durable, immediately available, infrequently accessed)
  - S3 One Zone - IA (even cheaper than IA, but only in one AZ)
  - Glacier - Archived data, where you can wait 3-5 hours before accessing.
  - Core fundamentals of the S3 objects: 
    - Key (name)
    - Value (data)
    - Version ID
    - Metadata
    - Subresources
      - ACL
      - Torrent
- Object-based storage only (for files)
- Not suitable to install an operating system on
- Success uploads will generate 200 status code
- Encyption
  - Client Side Encryption
  - Server Side Encryption
    - Server side encryption with Amazon S3 Managed Keys (SSE-S3)
    - Server side encryption with KMS (SSE-KMS)
    - Server side encryption with Customer Provided Keys (SSE-C)
- Control access to buckets using either a bucket ACL or using Bucket Policies
- By default Buckets are PRIVATE and all objects stored inside them are private

### S3 - Versioning Exam Tips
- Stores all versions of an object (including all writes and even if you delete an object)
- Great backup tool
- Once enabled, Versioning cannot be disabled, only suspended.
- Integrates with Lifecycle rules
- Versioning's MFA Delete capability, which uses MFA, can be used to provide an additional layer of security

### S3 - Cross Region Replication Exam Tips
- Versioning must be enabled on both the source and destination buckets
- Regions must be unique
- Files in an existing bucket are not replicated automatically. All subsequent updated files will be replicated automatically.
- You cannot replicate to multiple buckets or use daisy chaining
- Delete markers are replicated
- Deleting individual versions or delete markers will not be replicated. 
- Understand what Cross Region Replicaiton is at a high level

### S3 - Lifecycle Management
- Can be used in conjunction with versioning.
- Can be applied to current versions and previous versions  
- Read S3 FAQs before taking the exam!!
- Transition to the Standard-IA storage class (30 days after creation date)
- Archive to Glacier Storage Class (30 days after IA, if relevant)
- Permanently Delete

### Securing your buckets
- Setup access control to your buckets using:
  - Bucket Policies
  - Access Control Lists
- Can be configured to create access logs which log all requests made to the S3 Bucket. This can be done to another bucket.

### Encryption
- In Transit - sending to and from your bucket
  - SSL/TLS (HTTPS)
- At Rest
  - Server Side Encryption
    - S3 Managed Keys - SSE-S3
    - AWS Key Management Service, Managed Keys - SSE-KMS. Provides an audit trail.
    - Server Side Encryption with Customer Provided Keys - SSE-C
  - Client Side Encryption

# Cloud Front
Can be used to deliver your entire website, including dynamic, static, streaming, and interactive content using a global network of edge locations. Requests for your content are automatically routed to the nearest edge locations, so content is delivered with the best possible performance.

Optimized to work with other AWS's (S3, EC2, Elastic Load Balancing, Route 53). Works seamlessly with any non-AWS origin server, which stores the original, definitive versions of your files

### Key Terms/Exam Tips:
- Edge Location - location where content will be cached. Seperate to an AWS Region/AZ
- Origin - origin of all the files that the CDN will distribute. Can be either S3 bucket, and EC2 instance, Elastic Load Balancer or Route53. Can have multiple origins in the same distribution
- Distribution - This is the name given the CDN which consists of a collection of Edge Locations. Two types:
  - Web Distribution - typically used for websites
  - RTMP - Used for Media Streaming
- Edge locations are not just READ only, you can write to them too.
- Objects are cached for the life of the TTL (Time to Live) set by you
- You can clear cached objects, but you will be charged

# AWS Storage Gateway
Is a service that connects on-premises software appliance with cloud-based storage to provide seamless and secure integration between an organization's on-premises IT environment and AWS's storage infrastructure.
The service enables you to securely store data to the AWS cloud for scalable and cost-effective storage

### Four Types of Storage Gateways
- File Gateway (NFS) - store flat files (Word files, pdf, picture, videos, etc.) in S3. 
- Volumes Gateway (iSCSI) - Block storage. You would probably run operating systems on. Virtual harddisk you run VM on.
  - Stored Volumes - where you store entire copy of dataset on-premise
  - Cached Volumes - where you only store the most recently accessed data on-premise. Rest of data is backed up in Amazon
- Tape Gateway (VTL) - backup/archiving solution. Allows you to create virtual tapes and send to S3. Can use lifecycle policies to send them off to Glacier

### File Gateway
- Files stored as objects in your S3 buckets
- Accessed through Network File System mount point
- Ownership, permissions, and timestaps are durably stored in S3 in the user-metadata of the object associated with the file
- Can be managed as native S3 objects once transferred
- Bucket policies such as versioning, lifecycle management, and cross-region replication apply directly to objects stored in your bucket

### Volume Gateway
- presents applications with disk volumes using the iSCSI block protocol
- data written to these volumes can be asynchronously backed up as point-in-time snapshots of your volumes, and stored in the cloud as Amazon EBS(ELastic block store) snapshots.
- Snapshots are incremental backups that capture only changed blocks. All snapshot storage is compressed to minimize your storage charges
- Virtual hard disk on premise backed up on AMS

### Volume Gateway - Stored Volumes
- Store primary data locally, while asynchronously backing up that data to AWS
- Provide on-premises applications with low-latency access to their entire datasets, while providing durable, off-site backups.
- Can create storage volumes and mount them as iSCSI devices from your on-premises application servers
- Data written to your stored volumes in stored on your on-premises storage hardware
- Data is asynchronously backed up to S3 in the form of Amazon Elastic Block Store(EBS) snapshots
- 1 GB - 16 TB in size for Stored Volumes

### Volume Gateway - Cached Volumes
- Lets you use S3 as your primary data storage while retaining frequently accessed data locally in your storage gateway.
- Minimize the need to scale your on-premises storage infrastructure, while still providing your applications with low-latency access to their frequently accessed data
- Can create storage volumes up to 32 TiB in size and attach to them as iSCSI devices from your on-premises application servers
- Your gateway stores data that you write to these volumes in S3 and retains recently read data in your on-premises storage gateway's cache and upload butter storage
- 1GB - 32 TB in size for Cached Volumes.

### Volume Gateway - Tape Gateway
- Durable, cost-effective solution to archive your data in AWS Cloud.
- VTL interface lets you leverage your existing tape-based backup application infrastructure to store data on virtual tape cartridges that you create on your tape gateway
- Preconfigured with a media changer and tape drives, which are available to your existing client backup applications as iSCSI devices
- You add tape cartriges as you need to archive your data
- Supported by NetBackup, Backup Exec, Veeam, etc.

### Exam Tips
- File Gateway - for flat files, stored directly on S3. And for storage cost to a minimum
- Volume Gateway:
  - Stored Volumes - entire dataset is stored on site and is asynchronously backed up to S3
  - Cached Volumes - Entire Dataset is stored on S3 and the most frequently accessed data is cached on site
- Gateway Virtual Tape Library (VTL)
  - Used for backup and uses popular backup applications like NetBackup, Backup Exec, Veeam, etc.

# Snowball
Used to move large amounts of data into and out of AWS cloud using physical storage device for transport

### Types of Snowballs
- Snowball
- Snowball Edge
- Snowmobile

### Snowball
- petabyte-scale data transport solution that uses secure appliances to transfer large amounts of data into and out of AWS.
- Addresses common challenges with large-scale data transfers including high network costs, long transfer times, and security concerns
- Simple, fast, secure, little as 1/5 the cost of high-speed internet
- 80TB snowball in all regions
- Multiple layers of security to protect your data including tamper-resistnant enclosures, 256-bit encryption, and industry-standard Trusted Plateform Module (TPM) designed to ensure security and full chain-of custody of your data. 
- Once data transfer is processed and verified, AWS performs a software erasure of Snowball appliance

### Snowball Edge
- 100TB data transfer device with on-board storage and compute capabilities. Allow you to run lambda functions
- move large amounts of data into and out of AWS, as temporary storage tier for large local datasets, or to support local workloads in remote or offline locations
- Connects using standard storage interfaces, streamlining the data transfer process and minimizing setup and integration
- Can cluster together to form local storage tier and process your data on-premises, ensure application continue to run even when they are not able to access cloud

### Snowmobile
- Is exabyte-scale data transfer service used to move extremely large amounts of data to AWS.
- Can transfer up to 100PB per Snowmobile
- a 45-foot long ruggedizzed shipping contianer, pulled by a semi-trailer truck
- Makes it easy to move massive volumes of data to cloud (vido libraries, image repositories, complete data center migration)
- Secure, fast, and cost effective for transferring data

### Exam Tips
- Understand what Snowball is
- Understand what Import Export is. When you used to send your own disk of data to AWS
- Snowball can
  - Import to S3
  - Export from S3