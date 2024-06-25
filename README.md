# AWS Managed KMS Keys

While researching AWS KMS Keys and their security and access implications, we found it difficult to correlate all services that support AWS Managed KMS Keys.

## Interesting Notes

* In-use AWS Managed KMS Keys do not always appear in KMS (Console or via ListKeys API).
  
* A KMS `DescribeKey` operation must be run for the key to appear.

* `DescribeKey` is typically non-mutating.  But AWS services use `DescribeKey` to create AWS managed keys from a predefined AWS alias with no key ID.

## AWS Managed KMS Keys and their Key Policies
