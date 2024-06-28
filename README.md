# AWS Managed KMS Keys

While researching AWS KMS Keys and their security and access implications, we found it difficult to correlate all services that support AWS Managed KMS Keys.

## Interesting Notes

* In-use AWS Managed KMS Keys do not always appear in KMS (Console or via ListKeys API).
  
* A KMS `DescribeKey` operation must be run for the key to appear.

* `DescribeKey` is typically non-mutating.  But AWS services use `DescribeKey` to create AWS managed keys from a predefined AWS alias with no key ID.

* There is no cost for creation and storage of AWS managed keys.

## Services that have support for AWS Managed Keys

Total: 39 (us-east-1)
- AWS Certificate Manager (ACM)
- Amazon AppFlow
- AWS Backup
- AWS Cloud9
- AWS CodeArtifact
- AWS CodeCommit
- Amazon Connect
- Amazon DynamoDB Accelerator (DAX)
- AWS Database Migration Service (AWS DMS)
- Amazon DynamoDB
- Amazon Elastic Block Store (Amazon EBS)
- Amazon Elastic Container Registry (Amazon ECR)
- Amazon Elastic Kubernetes Service (Amazon EKS)
- Amazon ElastiCache
- Amazon Elastic File System (EFS)
- Amazon OpenSearch Service
- Amazon FSx
- AWS Glue
- EC2 Image Builder
- Amazon Managed Streaming for Kafka (MSK)
- Amazon Kendra
- Amazon Kinesis Data Streams
- Amazon Kinesis Video Streams
- AWS Lambda
- Amazon Lex
- Amazon Lightsail
- Amazon MQ
- Amazon Relational Database Service (Amazon RDS)
- Amazon Redshift
- Amazon Simple Storage Service (Amazon S3)
- AWS Secrets Manager
- Amazon Simple Email Service(Amazon SES)
- Amazon Simple Notification Service (Amazon SNS)
- Amazon Simple Queue Service (Amazon SQS)
- AWS Systems Manager
- Amazon Timestream
- Amazon Translate
- Amazon WorkSpaces
- AWS X-Ray

## AWS Managed KMS Keys and their Key Policies

For corresponding AWS Managed KMS Keys and their Key Policies, please see files in repository that correspond to each AWS Managed KMS Key by service alias.

### Notes
- Key policies are pulled from a reference AWS Account and the Account Number is scrubbed and changed to the placeholder '123412341234'.
- All key policies are pulled from AWS region `us-east-1`
