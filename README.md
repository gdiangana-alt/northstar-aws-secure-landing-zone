# NorthStar AWS Secure Landing Zone

Verified multi-account AWS security implementation in us-east-2 using AWS Organizations and AWS Control Tower.

## Implemented governance

- AWS Organizations with all features enabled
- Control Tower landing zone v4.0 with automatic account enrollment
- Security and Sandbox organizational units
- Central AWS Config in NorthStar Governance
- Organization-wide CloudTrail in NorthStar Log Archive
- Governed NorthStar Secure Workloads account with inherited Config baseline
- Preventive control: Disallow public write access to S3 buckets
- Root MFA and a monthly AWS budget alert

## Validation

Control Tower reports an ACTIVE, IN_SYNC landing zone. The workload account recorder is active, and the organization CloudTrail has log-file validation enabled.
