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