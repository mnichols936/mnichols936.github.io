# Lab 1 – AWS Account Governance

This lab demonstrates how to establish foundational governance and security controls for AWS accounts, aligned with SOC 2, HIPAA, and NIST CSF requirements.

## Resources
- 🔗 [Source Lab README](https://github.com/ajy0127/grc_portfolio/tree/main/labs/lab-1-account-governance) – official instructions and full lab documentation.

---

## Overview
This lab focused on implementing foundational governance and security controls for AWS accounts using IAM Identity Center, CloudTrail, Config, Security Hub, and Cost Explorer. The goal was to establish a secure, compliant, and cost-conscious environment aligned with the AWS Well-Architected Framework.

## What I Did
- Secured the root account with Multi-Factor Authentication (MFA).
- Enabled **IAM Identity Center (SSO)** and created permission sets (AdministratorAccess, ReadOnlyAccess).
- Configured **CloudTrail** to capture activity across all regions and integrated with **CloudWatch Logs**.
- Created **CloudWatch alarms** to detect root logins, console sign-in failures, and IAM changes; linked them to an SNS topic for notifications.
- Enabled **AWS Config** with compliance rules (MFA enforcement, password policies, S3 public access prevention).
- Deployed a CloudFormation template to automate compliance monitoring.
- Activated **Security Hub**, enabling AWS Foundational Security Best Practices and CIS AWS Benchmark v1.4.
- Integrated partner services: GuardDuty, Inspector, and IAM Access Analyzer.
- Configured **Cost Explorer** and budget alerts to monitor monthly usage and avoid unexpected charges.

## Challenges / Issues
- The CloudWatch alarm creation process has changed in the AWS Console since the lab was written. I had to adjust JSON filter syntax to align with updated metric filters.
- IAM Identity Center setup required careful mapping of permission sets to groups — initially misconfigured “ReadOnlyAccess,” which I corrected by reassigning permission boundaries.

## Key Learnings
- **Identity Governance**: IAM Identity Center simplifies least-privilege enforcement and provides scalable group-based access.
- **Audit Readiness**: CloudTrail + Config ensure every action is logged and continuously validated against compliance rules.
- **Centralized Security**: Security Hub aggregates findings from multiple services, streamlining remediation.
- **Shared Responsibility Model**: AWS provides strong tools, but securing the configuration is entirely on the account owner.

## Business Value
- **SOC 2**: Demonstrates strong access control and monitoring aligned with Trust Service Criteria.  
- **HIPAA**: Satisfies requirements for access management, audit controls, and transmission security.  
- **NIST CSF**: Strengthens Identify, Protect, Detect domains with clear governance and continuous monitoring.  
- **Operational Efficiency**: Automating alerts and compliance rules reduces manual oversight.

## Next Steps
- Extend AWS Config rules with Lambda-based auto-remediation (e.g., automatically disabling public S3 buckets).
- Integrate budget alerts with Slack for real-time notifications.
- Expand IAM permission sets to reflect more granular job roles.
- Explore multi-account governance via AWS Organizations.
