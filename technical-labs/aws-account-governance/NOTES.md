# AWS Account Governance Lab

## Overview
Implemented foundational governance and security controls for AWS accounts using IAM Identity Center, CloudTrail, Config, Security Hub, and Cost Explorer.

## What I Did
- Secured root account with MFA.
- Set up IAM Identity Center with Administrator/ReadOnly permission sets.
- Configured CloudTrail + CloudWatch with alarms (root logins, sign-in failures).
- Enabled AWS Config with compliance rules via CloudFormation.
- Activated Security Hub with CIS & AWS Security Best Practices.
- Added budget alerts in Cost Explorer.

## Challenges / Issues
- CloudWatch alarm creation UI changed → adjusted JSON filter syntax.
- Misconfigured ReadOnly group in IAM Identity Center → fixed permission mapping.

## Key Learnings
- IAM Identity Center enforces least-privilege at scale.
- CloudTrail + Config = audit-ready continuous monitoring.
- Security Hub centralizes findings, reduces blind spots.
- Shared responsibility: AWS provides tools, but secure configs are on the customer.

## Business Value
- SOC 2: trust service criteria (security & availability).
- HIPAA: enforces access controls & audit logging.
- NIST CSF: strengthens Identify, Protect, Detect domains.

## Next Steps
- Add Lambda auto-remediation to AWS Config rules.
- Send budget alerts to Slack instead of email.
- Expand IAM permission sets for finer roles.
