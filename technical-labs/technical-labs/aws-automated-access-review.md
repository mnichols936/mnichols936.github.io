# AWS Automated Access Review Lab

This lab demonstrates deployment of an automated IAM access review system in AWS. It uses serverless architecture (Lambda, SES, Bedrock) to evaluate IAM security risks, generate compliance-ready reports, and email stakeholders on a recurring schedule.

## Resources
- 📝 [My Notes](NOTES.md) – execution details, challenges, and learnings.
- 🔗 [Upstream Project README](https://github.com/ajy0127/aws_automated_access_review)

## Why I Chose This Lab
I ran this lab to practice **automating a traditional GRC process (access reviews)** using AWS-native tooling. This bridges the gap between manual compliance checks and automated cloud-native auditing.

## Key AWS Services
- AWS Security Hub  
- IAM Access Analyzer  
- Amazon SES (email delivery)  
- Amazon Bedrock (AI-powered summaries)  
- AWS Lambda + CloudFormation (serverless automation)  
