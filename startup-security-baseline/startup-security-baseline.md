# Startup Security Baseline
[Reference Link](https://catalog.workshops.aws/startup-security-baseline/en-US)

## Introduction

This project aims to provide step-by-step instructions to improve your security posture. This workshop is a practical guide that complements the [AWS Startup Security Baseline - Prescriptive Guidance](https://docs.aws.amazon.com/prescriptive-guidance/latest/aws-startup-security-baseline/welcome.html) document.

Security is important to help you earn the trust of your customers, regulators and auditors. The SSB is a set of controls we believe all startups should implement  **as a minimum foundation**  to build their businesses securely on AWS without decreasing their agility. These controls will form the basis of your security posture and are focused on securing the credentials with the most permissions, enabling basic logging, updating contact information & putting in some initial guardrails to help you put a boundary around your data.

**Task Progress Note:**
 - [x] Task Accomplished 
 - [ ] Task Unaccomplished 

# Part I - Securing your AWS Account

## 1.1 Accurate Account Information
Accurate account information prevents you from losing access to your account. When AWS needs to contact you about your AWS account , we use the contact information defined in the AWS Management Console, including the email address used to create the account and those listed under Alternate Contacts.
###  Controls Implemented in this Section

-   [ACCT.01 - Set account-level contacts to valid email distribution lists](https://docs.aws.amazon.com/prescriptive-guidance/latest/aws-startup-security-baseline/acct-01.html)

###  What accomplished
 - [x] -   Ensured that your  _Root Account Email_  is valid to avoid losing access to your account
 - [x] -   Added  _Alternate Contacts_  so that your teams are accurately notified
 - [x] -   Added  _Security Challenge Questions_

## 1.2 Protect the Root User
Your root user (the email you used to register the AWS account) is very powerful and grants unlimited access to your account and resources. In this module, we will work to protect your root user.

### Controls Implemented in this Section
-   [ACCT.02 - Restrict use of the root user](https://docs.aws.amazon.com/prescriptive-guidance/latest/aws-startup-security-baseline/acct-02.html)
-   [ACCT.05 - Require Multi-Factor Authentication (MFA) to log in](https://docs.aws.amazon.com/prescriptive-guidance/latest/aws-startup-security-baseline/acct-05.html)

###  What accomplished
 - [x] -   Configured MFA for your Root user
 - [x] -   Deleted your Root Account access keys

## 1.3 Create Users for Human Identities
Instead of using your root user, you should create and use either an IAM Admin User or an SSO Admin User for day-to-day tasks.

### Controls Implemented in this Section

-   [ACCT.03 - Configure console access for each user](https://docs.aws.amazon.com/prescriptive-guidance/latest/aws-startup-security-baseline/acct-03.html)
-   [ACCT.05 - Require Multi-Factor Authentication (MFA) to log in](https://docs.aws.amazon.com/prescriptive-guidance/latest/aws-startup-security-baseline/acct-05.html)
-   [ACCT.06 - Enforce a password policy](https://docs.aws.amazon.com/prescriptive-guidance/latest/aws-startup-security-baseline/acct-06.html)

###  What accomplished
#### 1.3.1 Create Users in SSO
 - [ ] -   Enabled IAM User and Role Access to billing
 - [ ] -   Set up AWS SSO with the SSO identity store.
 - [ ] -   Enforced MFA for Users
 - [ ] -   Created an Admin User in SSO and assign them to accounts to replace your root user.
 - [ ] -   Created other users for the rest of your team.

***Note: AWS IAM Identity Center is the updated console for the features of AWS Single Sign-On (AWS SSO)***

#### 1.3.2 Create Users in IAM
 - [ ] -   Created an IAM Admin user for the team to protect your Root user
 - [ ] -   Configured MFA for the IAM Admin User
 - [ ] -   Set up a password policy for your IAM Users.
 - [ ] -   Created other IAM users for your team.

## 1.4 Use User Groups

User Groups enable applying permission policies to the collection of IAM Users that are within the group. Create User Groups that align to human operator job functions and attach appropriate AWS-managed policies or AWS-defined Permission Sets to get started with granting least privilege.

### Controls Implemented in this Section
-   [ACCT.04 - Assign permissions by using IAM user groups](https://docs.aws.amazon.com/prescriptive-guidance/latest/aws-startup-security-baseline/acct-04.html)

###  What accomplished
#### 1.4.1 Create SSO User Groups
 - [ ] -   Created groups for specific job functions on your team to easily manage access permissions.
 - [ ] -   Added Permission Sets to limit the amount of permissions that users receive.

#### 1.4.2 Create IAM User Groups

 - [ ] -   Created groups for specific job functions on your team to easily manage IAM permissions.
 - [ ] -   Added  **AWS-managed policies**  to limit the amount of permissions that users receive.

## 1.5 Turn CloudTrail On

Logging and monitoring are important parts of a robust security plan.  [AWS CloudTrail](https://aws.amazon.com/cloudtrail/) monitors and records account activity across your AWS infrastructure, ensuring that you know  **who**  is doing  **what**  and  **where**  in your AWS account.

### Controls Implemented in this Section
-   [ACCT.07 - Deliver CloudTrail logs to a protected S3 bucket](https://docs.aws.amazon.com/prescriptive-guidance/latest/aws-startup-security-baseline/acct-07.html)

###  What accomplished

 - [ ]  -   Understanding CloudTrail Events
 - [ ]  -   Creating CloudTrail Trail (via CloudFormation)
 - [ ]  -   Creating CloudTrail Trail (Manually)
 - [ ] -   Turned CloudTrail on and configured it to send logs to S3
 - [ ] -   Ensured that CloudTrail logs are encrypted
 - [ ] -   Protected the S3 Bucket by blocking public access
 - [ ] -   Integrate CloudWatch Logs with CloudtTrail 

## 1.6 Prevent Public Access to Private S3 Buckets

Prevent public access to your private S3 buckets due to bucket policy misconfiguration by enabling the Block Public Access setting for each bucket. If you have no current or future use cases for a public S3 bucket, enable this setting at the AWS account level. This setting prevents policies that enable public access from taking effect.

### Best Practice - Account Level S3 BPA

A best practice is to turn on  **S3 Block Public Access at the Account Level**. This is easier to manage and enforce than turning it on for individual buckets.

If you need to host a static website on S3 there are two recommended options.

-   You can use Amazon CloudFront with an S3 REST API endpoint as the origin, with access restricted by an Origin Access Identity. This  [blog post](https://aws.amazon.com/premiumsupport/knowledge-center/cloudfront-serve-static-website/) explains the process in more detail.
-   You can place buckets with sensitive data and buckets with non-sensitive data in different accounts. You can then use S3 BPA on the account containing sensitive data.

### Controls Implemented in this Section
-   [ACCT.08 - Prevent public access to private S3 buckets](https://docs.aws.amazon.com/prescriptive-guidance/latest/aws-startup-security-baseline/acct-08.html)

###  What accomplished

 - [ ] -   Blocked all public access to your S3 buckets to prevent public access due to misconfiguration.
 - [ ] -   Turn on S3 Block Public Access at the account level
 - [ ] -   Turn on S3 Block Public Access at the bucket level.

## 1.7 Configure Alarms

In this workshop, we will set up a billing alarm and an alarm for root account use. Thhese alarms can notify you if a malicious actor has accessed your account and deployed resources.

The billing alarm will notify you if your billing is projected to exceed a certain amount. Use forecasted cost notifications  _as a last line of defense_  to detect and terminate unauthorized resources.

The root account alarm will notify you if any one accesses your root account. When you receive the notification, you can take action if this access is unintended.

### Controls Implemented in this Section
-   [ACCT.10 - Configure Cost Budgets to monitor your spend](https://docs.aws.amazon.com/prescriptive-guidance/latest/aws-startup-security-baseline/acct-10.html)

###  What accomplished

 - [ ] -   Set up billing alarms using CloudWatch Alarms to alert you when spending has hit a threshold
 - [ ]  -  Create billing alerts (via CloudFormation)
 - [ ]  -  Create billing alerts (Manually)
 - [ ] -   Set up root account use alarm to inform you when someone logs into your root account (via CloudFormation)
 - [ ] -   Set up root account use alarm to inform you when someone logs into your root account (Manually)

## 1.8 Delete unused VPCs, Subnets & Security Groups
Delete or disable any resources that are not being used to reduce the opportunity for security issues. A default VPC is created automatically in every Region in a new AWS account that enables the assignment of public IP addresses in public subnets. While this makes it easy for you to get started building in a new region, it also introduces the risk of unintended exposure of resources.

If the default VPC in each region is not in use, it should be deleted. Remember to delete the default VPC in  **all regions**  and not just the region(s) you may be deploying workloads.

### Controls Implemented in this Section
-   [ACCT.09 - Delete unused VPCs, subnets, security groups](https://docs.aws.amazon.com/prescriptive-guidance/latest/aws-startup-security-baseline/acct-09.html)

###  What accomplished
 - [ ] -   Delete unused VPCs
 - [ ] -   Delete unused subnets
 - [ ] -   Delete unused security groups

## 1.9 Enable AWS Trusted Advisor

[AWS Trusted Advisor](https://aws.amazon.com/premiumsupport/technology/trusted-advisor/) passively scans your AWS infrastructure for high risk or high impact issues related to security, performance, cost, and reliability, with detailed information about affected resources and remediation recommendations.

Review Trusted Advisor findings on a recurring basis and remediate items as necessary. Business and Enterprise Support customers can subscribe to a weekly findings email through the web management console.

### Controls Implemented in this Section
-   [ACCT.12 - Monitor for and resolve high-risk issues by using Trusted Advisor](https://docs.aws.amazon.com/prescriptive-guidance/latest/aws-startup-security-baseline/acct-12.html)

###  What accomplished
 - [ ] -   Set up Trusted Advisor to evaluate your account with checks based on AWS best practices
 - [ ] -   Made Trusted Advisor more prominent on the home screen of the console

## 1.10 Enable GuardDuty

[Amazon GuardDuty](https://aws.amazon.com/guardduty/) is an intelligent threat detection service that continuously monitors for malicious or unauthorized behavior to protect your AWS accounts, workloads, Kubernetes clusters, and data stored in Amazon S3 and delivers detailed security findings for visibility and remediation. Threats that GuardDuty is able to detect include cryptocurrency mining activity, Tor clients and relays, and compromised IAM credentials.

Enable GuardDuty and respond to findings to stop malicious or unauthorized behavior occurring within your AWS account.

### Controls Implemented in this Section
-   [ACCT.11 - Enable and respond to GuardDuty notifications](https://docs.aws.amazon.com/prescriptive-guidance/latest/aws-startup-security-baseline/acct-11.html)

###  What accomplished
 - [ ] -   Set up GuardDuty in a single AWS Account 
 - [ ] -   Set up GuardDuty in a multi-account AWS Organizations.
 - [ ] -   Learn how to read GuardDuty findings
 - [ ] -   Set up an SNS Topic
 - [ ] -   Set up a CloudWatch Event for GuardDuty Findings





