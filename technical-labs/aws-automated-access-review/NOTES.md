# AWS Automated Access Review Lab - Notes

## Overview
Deployed a serverless tool that automates IAM security assessments, generates CSV + AI-powered executive reports, and emails them to stakeholders.

## What I Did
- Verified email in SES for report delivery.
- Deployed CloudFormation stack with Lambda + supporting services.
- Ran immediate report → generated CSV of IAM misconfigurations and AI summary from Bedrock.
- Validated integration with Security Hub and IAM Access Analyzer.

## Challenges / Issues
- Environment setup
- Initial SES verification email landed in spam; fixed by whitelisting sender.
- Lambda timeout hit once during testing on a large account → adjusted memory and timeout.

  ## Challenges / Issues
- Windows Compatibility: Bash scripts failed; worked with AI tool to create PowerShell equivalents
- Limited CLI Permissions: Got AccessDenied errors; used AWS Console for service enablement  
- Lambda Deployment: Automated deployment failed; required manual packaging and troubleshooting
- Regional Mismatch: Scripts defaulted to us-east-1, CLI used us-east-2

## Key Learnings
- Automating IAM reviews reduces audit prep time (SOC 2, HIPAA).
- Bedrock can turn raw CSV data into compliance-friendly summaries.
- Serverless architecture minimizes cost (~$1/month) while scaling up to 2000+ resources.

## Business Value
- SOC 2 Type II: enables monthly evidence generation.
- HIPAA: supports ongoing access review requirement (164.308(a)(3)).
- Reduces manual review cycles and provides timestamped, repeatable reports.

## Next Steps
- Extend automation to cover privilege escalation checks.
- Send findings to Slack in addition to email.
- Build dashboard view for ongoing tracking beyond static reports.
