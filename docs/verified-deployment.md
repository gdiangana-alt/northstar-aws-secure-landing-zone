# Verified AWS Deployment Evidence

Verified on 2026-10-17 in us-east-2.

## Landing zone status

| Check | Verified result |
| --- | --- |
| AWS Control Tower version | 4.0 |
| Landing zone status | ACTIVE |
| Drift status | IN_SYNC |
| Automatic account enrollment | Enabled |
| Central AWS Config | Enabled |
| Centralized CloudTrail | Enabled |

## Account model

- NorthStar Governance: central AWS Config integration
- NorthStar Log Archive: organization-wide CloudTrail retention
- NorthStar Secure Workloads: governed Sandbox workload account

## Validated controls

- Sandbox ConfigBaseline enablement: SUCCEEDED
- Workload Config recorder: aws-controltower-BaselineConfigRecorder, Recording=True, LastStatus=SUCCESS
- Disallow public write access to S3 buckets: SUCCEEDED, inheritance IN_SYNC
- Organization trail: aws-controltower-BaselineCloudTrail
- CloudTrail log-file validation: enabled

## Retention configuration

- AWS Config and CloudTrail log buckets: 365 days
- Access-log buckets: 3,650 days

Account identifiers, access credentials, and log contents are intentionally excluded.
