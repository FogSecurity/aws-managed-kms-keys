# AWS Managed KMS Keys

While researching AWS KMS Keys and their security and access implications, we found it difficult to correlate all services that support AWS Managed KMS Keys. Visibility of usage of [AWS Managed KMS Keys](https://docs.aws.amazon.com/kms/latest/developerguide/concepts.html#aws-managed-cmk) and their corresponding key policies can be low and may have security and application implications.  AWS Managed KMS Keys are keys managed by AWS but exist within your own AWS Account with corresponding key policies.  These sometimes are the default key applied to resources.  

This repository contains a listing of AWS Managed KMS Keys and their associated policies.  There's a periodic scheduled job that will run and update the listings and data.

AWS Managed KMS Keys:
- There's no central documentation on which AWS Services provide AWS Managed KMS Keys.  There are service-specific pages, but no central place to review available encryption options and provided AWS Managed KMS Keys.
- Not all AWS Managed KMS Keys appear in KMS (Console or via ListKeys API) even if they're in use by your resources.  This can lead to impaired [visibility of AWS Managed KMS Keys](https://docs.aws.amazon.com/kms/latest/developerguide/viewing-keys-cli.html).
- A KMS `DescribeKey` operation must be run for the AWS Managed key to appear.
- AWS Managed Keys may differ by service with different conditions and policy blocks.
- `DescribeKey` is typically non-mutating.  But AWS services use `DescribeKey` to create AWS managed keys from a predefined AWS alias with no key ID.
- There is no cost for creation and storage of AWS managed keys.
- AWS completely manages properties of AWS managed keys, key rotation, their key policies, and their deletion schedule.  Thus, you cannot manage them.  The AWS service that creates them uses them on your behalf.

Impact:
- Implicit Access for Applications and other IAM Principals.
- Access granted by the KMS Managed Key and the associated key policy may have security and architectural implications.
- Application Architecture and Account and Region Boundaries.

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
