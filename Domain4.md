# Domain 4: ML Solution Monitoring, Maintenance, and Security (24%)

---

# Task 4.1: Monitor Model Inference

## Overview

Once a model is deployed, it must be continuously monitored to ensure:

- Prediction quality remains high
- Data quality remains consistent
- Infrastructure performs correctly
- Drift is detected early

---

# Model Drift

## Definition

Model drift occurs when model performance degrades over time due to changes in data patterns.

---

## Causes of Drift

### Changes in Customer Behavior

Example:

Customers previously purchased Product A.

Now they purchase Product B.

---

### Seasonal Changes

Example:

Holiday shopping behavior differs from regular months.

---

### Market Changes

Example:

Economic conditions affect customer spending habits.

---

# Types of Drift

## Data Drift (Feature Drift)

### Definition

Input data distribution changes.

### Example

Training Data Age Range:

20-40

Production Data Age Range:

50-80

### Impact

Reduced prediction accuracy.

---

## Concept Drift

### Definition

Relationship between features and target changes.

### Example

Customer behavior changes after a new product launch.

### Impact

Model predictions become unreliable.

---

## Label Drift

### Definition

Target variable distribution changes.

### Example

Fraud rate increases significantly over time.

---

### Exam Tip

Data Drift = Input changes

Concept Drift = Relationship changes

Label Drift = Output changes

---

# SageMaker Model Monitor

## Purpose

Monitor deployed models in production.

---

## Capabilities

### Data Quality Monitoring

Checks:

- Missing values
- Unexpected values
- Schema changes

---

### Model Quality Monitoring

Tracks:

- Accuracy
- Precision
- Recall
- F1 Score

---

### Bias Monitoring

Detects fairness issues.

---

### Feature Attribution Monitoring

Tracks changes in feature importance.

---

### Exam Tip

Need production monitoring?

Choose SageMaker Model Monitor.

---

# Monitoring Data Quality

## Common Issues

### Missing Values

Unexpected increase in null values.

---

### Schema Drift

Columns added or removed.

---

### Data Type Changes

Example:

Age column changes from Integer to String.

---

# SageMaker Clarify

## Purpose

Detect bias and explain predictions.

---

## Capabilities

### Bias Detection

Before Training:
- Dataset Bias

After Training:
- Prediction Bias

---

### Explainability

Provides:

- Feature Importance
- SHAP Values

---

### Frequently Tested

Yes

---

# A/B Testing

## Purpose

Compare multiple model versions.

---

## Example

Model A:
Current Production Model

Model B:
New Candidate Model

---

## Benefits

- Safer deployment
- Better decision making

---

## Exam Tip

Compare two models in production?

Use A/B Testing.

---

# Shadow Testing

## Purpose

Test a new model using real traffic without affecting users.

---

## Benefits

- No user impact
- Real-world validation

---

### Exam Tip

Need production validation without serving predictions?

Use Shadow Testing.

---

# Monitoring Pipelines

## Goals

Detect:

- Failed processing jobs
- Failed training jobs
- Endpoint failures
- Data quality issues

---

# CloudWatch Alarms

## Purpose

Send alerts when thresholds are exceeded.

---

## Examples

Alert when:

- CPU > 80%
- Latency > 500ms
- Endpoint failures increase

---

# Task 4.2: Monitor and Optimize Infrastructure and Costs

---

# Key Infrastructure Metrics

## Utilization

Measures resource usage.

Examples:

- CPU Utilization
- Memory Utilization

---

## Throughput

Amount of work completed.

Example:

Predictions per second.

---

## Availability

Percentage of uptime.

---

## Scalability

Ability to handle increased workload.

---

## Fault Tolerance

Ability to continue operating during failures.

---

# Amazon CloudWatch

## Purpose

Central monitoring service.

---

## Monitors

- CPU
- Memory
- Network
- Disk
- Endpoints

---

## Components

### Metrics

Numerical measurements.

---

### Logs

Application and system logs.

---

### Alarms

Automatic notifications.

---

### Dashboards

Visual monitoring.

---

### Exam Tip

Most monitoring questions point to CloudWatch.

---

# CloudWatch Logs Insights

## Purpose

Search and analyze logs.

---

## Use Cases

- Error investigation
- Troubleshooting
- Performance analysis

---

# AWS X-Ray

## Purpose

Distributed tracing service.

---

## Benefits

Tracks:

- API latency
- Service bottlenecks
- Dependency issues

---

### Exam Tip

Need request tracing?

Choose AWS X-Ray.

---

# AWS CloudTrail

## Purpose

Records API activity.

---

## Tracks

- User actions
- Resource changes
- Security events

---

## Example

Determine:

Who deleted a SageMaker endpoint?

CloudTrail provides the answer.

---

### Exam Tip

Audit activity → CloudTrail

Monitor performance → CloudWatch

---

# Infrastructure Optimization

## AWS Compute Optimizer

### Purpose

Recommend optimal instance sizes.

---

### Benefits

- Lower cost
- Better performance

---

# SageMaker Inference Recommender

## Purpose

Recommend best inference instance.

---

## Evaluates

- Latency
- Throughput
- Cost

---

### Exam Tip

Need endpoint sizing recommendations?

Choose Inference Recommender.

---

# Cost Management Tools

## AWS Cost Explorer

### Purpose

Analyze AWS spending.

---

### Features

- Cost trends
- Forecasting
- Service breakdown

---

## AWS Budgets

### Purpose

Set spending limits.

---

### Example

Monthly Budget:

$500

Alert at:

80%

100%

---

## AWS Trusted Advisor

### Purpose

Provides optimization recommendations.

---

### Areas Covered

- Cost
- Security
- Performance
- Fault Tolerance

---

# Resource Tagging

## Purpose

Track costs by resource.

---

## Example

Environment=Production

Department=ML

Project=FraudDetection

---

### Benefits

- Cost allocation
- Reporting
- Governance

---

# Purchasing Options

## On-Demand Instances

### Advantages

- Flexible
- No commitment

### Disadvantages

- Most expensive

---

## Reserved Instances

### Advantages

- Lower cost

### Disadvantages

- Long-term commitment

---

## Spot Instances

### Advantages

- Up to 90% savings

### Disadvantages

- Interruptions possible

### Best For

Training jobs

---

## SageMaker Savings Plans

### Purpose

Reduce SageMaker costs.

---

### Exam Tip

Training workloads → Spot Instances

Long-term workloads → Savings Plans

---

# Troubleshooting Performance

## High Latency

Possible Causes:

- Insufficient endpoint capacity
- Wrong instance type
- Increased traffic

Solutions:

- Auto Scaling
- Larger instances
- GPU deployment

---

## Capacity Issues

Possible Causes:

- Service Quotas
- Scaling limits

Solutions:

- Increase quotas
- Adjust scaling policies

---

# Task 4.3: Secure AWS Resources

---

# Security Overview

Goals:

- Confidentiality
- Integrity
- Availability

---

# IAM (Identity and Access Management)

## Purpose

Control access to AWS resources.

---

# IAM Components

## Users

Human identities.

---

## Groups

Collection of users.

---

## Roles

Temporary permissions.

### Common Example

SageMaker accesses S3 using IAM Roles.

---

## Policies

JSON documents defining permissions.

---

### Exam Tip

AWS services should use IAM Roles instead of access keys.

---

# Principle of Least Privilege

## Definition

Grant only the permissions required.

---

## Example

Instead of:

S3 Full Access

Use:

Read access to a specific bucket

---

### Frequently Tested

Yes

---

# SageMaker Security Features

## IAM Integration

Fine-grained access control.

---

## VPC Integration

Private network access.

---

## Encryption

At rest and in transit.

---

# AWS KMS

## Purpose

Encryption key management.

---

## Uses

- S3 Encryption
- EBS Encryption
- SageMaker Encryption

---

### Exam Tip

Encryption questions usually involve AWS KMS.

---

# Encryption Types

## Encryption at Rest

Protects stored data.

Examples:

- S3
- EBS
- EFS

---

## Encryption in Transit

Protects moving data.

Examples:

- TLS
- HTTPS

---

# AWS Secrets Manager

## Purpose

Store credentials securely.

---

## Examples

- Database passwords
- API keys
- Tokens

---

### Exam Tip

Never store credentials directly in code.

Use Secrets Manager.

---

# Amazon Macie

## Purpose

Discover sensitive data.

---

## Detects

- PII
- Financial data
- Sensitive documents

---

# Network Security

---

# Amazon VPC

## Purpose

Private network environment.

---

# Subnets

### Public Subnet

Internet accessible.

---

### Private Subnet

No direct internet access.

---

# Security Groups

## Purpose

Instance-level firewall.

---

## Controls

- Inbound traffic
- Outbound traffic

---

### Exam Tip

Security Groups are stateful.

---

# Monitoring Security

## CloudTrail

Tracks:

- User activity
- API calls

---

## CloudWatch

Tracks:

- Security events
- Alarms

---

# Compliance Requirements

## PII

Personally Identifiable Information

Examples:

- Name
- Phone Number
- Aadhaar Number

---

## PHI

Protected Health Information

Healthcare data.

---

# Security Best Practices

- Use IAM Roles
- Follow Least Privilege
- Encrypt data with KMS
- Store secrets in Secrets Manager
- Enable CloudTrail
- Use VPC isolation
- Monitor with CloudWatch
- Rotate credentials regularly

---

# Domain 4 Quick Revision

Remember:

- Model Monitor → Production Monitoring
- Clarify → Bias + Explainability
- A/B Testing → Compare models
- Shadow Testing → Safe production testing
- CloudWatch → Monitoring
- CloudTrail → Auditing
- X-Ray → Request tracing
- Compute Optimizer → Instance recommendations
- Inference Recommender → Endpoint recommendations
- Cost Explorer → Cost analysis
- Budgets → Spending alerts
- IAM Roles → Service permissions
- KMS → Encryption
- Secrets Manager → Credential storage
- Macie → PII detection
- VPC → Network isolation
- Least Privilege → Security best practice
- Spot Instances → Cheapest training option