# AWS Automated Access Review Lab - Notes

## Overview
Deployed a serverless tool that automates IAM security assessments, generates CSV + AI-powered executive reports, and emails them to stakeholders.

## What I Did
- Verified email in SES for report delivery.
- Deployed CloudFormation stack with Lambda + supporting services.
- Ran immediate report → generated CSV of IAM misconfigurations and AI summary from Bedrock.
- Validated integration with Security Hub and IAM Access Analyzer.

  ## Challenges / Issues
- Windows Compatibility: Bash scripts failed; created PowerShell equivalents by swapping ".sh" for ".ps1"
- Model Compatibility Discovery: Original lab used Claude v2, but testing revealed multiple models work with different approaches:
  - Claude v2: Works with original code (direct model access)
  - Claude 3.5 Sonnet: Requires inference profile modifications
  - Claude 3 Opus: Requires inference profile modifications
  - Claude Opus 4.1: Works with original code (backward compatible)
  - Successfully modified code for Claude 3 Opus by updating model ID format and redeploying

## Key Learnings
- Automating IAM reviews reduces audit prep time (SOC 2, HIPAA).
- Bedrock can turn raw CSV data into compliance-friendly summaries.
- Serverless architecture minimizes cost (~$1/month) while scaling up to 2000+ resources.
- Systematic testing across Claude model versions revealed compatibility patterns rather than universal requirements (Will change with AWS removing access request step entirely, regardless of model choice)

## Business Value
- SOC 2 Type II: enables monthly evidence generation.
- HIPAA: supports ongoing access review requirement (164.308(a)(3)).
- Reduces manual review cycles and provides timestamped, repeatable reports.

## Next Steps
- Extend automation to cover privilege escalation checks.
- Send findings to Slack in addition to email.
- Build dashboard view for ongoing tracking beyond static reports.
