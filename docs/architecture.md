# Architecture

## Purpose

NorthStar establishes a governed multi-account AWS foundation in `us-east-2` for secure workload delivery, centralized logging, configuration visibility, and preventive guardrails.

## Account and governance design

| Layer | AWS account or OU | Responsibility |
| --- | --- | --- |
| Management | Guy | Organization administration, billing, and landing-zone governance |
| Security | NorthStar Governance | Central AWS Config integration and governance evidence |
| Security | NorthStar Log Archive | Organization-wide CloudTrail retention and log-file validation |
| Sandbox | NorthStar Secure Workloads | Governed workload account for secure service deployment |

## Control flow

1. AWS Organizations provides the account boundary and organizational-unit hierarchy.
2. AWS Control Tower governs `us-east-2`, manages enrollment, and applies baselines.
3. The Sandbox ConfigBaseline provisions AWS Config recording for enrolled workload accounts.
4. The Sandbox S3 public-write guardrail is inherited by the workload account.
5. CloudTrail sends organization activity to the dedicated Log Archive account.

## Operating boundaries

- Root access is protected with MFA; root access keys are absent.
- Daily administration uses delegated roles and short-lived sessions.
- Workloads belong in member accounts, not the management account.
- Account IDs, credentials, CloudTrail records, and Terraform state are excluded from this repository.
