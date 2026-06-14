# Domain 3: Deployment and Orchestration of ML Workflows (22%)

---

# Task 3.1: Select Deployment Infrastructure Based on Existing Architecture and Requirements

## Overview

After training a model, the next step is deployment. The deployment method depends on:

- Latency requirements
- Cost constraints
- Traffic volume
- Inference frequency
- Infrastructure requirements

---

# Inference Types

## Real-Time Inference

### Description

Returns predictions immediately.

### Use Cases

- Fraud Detection
- Recommendation Systems
- Chatbots
- Real-Time Personalization

### AWS Service

- SageMaker Real-Time Endpoint

### Advantages

- Low latency
- Immediate predictions

### Disadvantages

- Higher cost
- Endpoint must remain active

---

## Batch Inference

### Description

Processes large datasets at scheduled intervals.

### Use Cases

- Monthly Reporting
- Sales Forecasting
- Customer Segmentation

### AWS Service

- SageMaker Batch Transform

### Advantages

- Lower cost
- No active endpoint required

### Disadvantages

- Higher latency

---

## Asynchronous Inference

### Description

For requests that take a long time to process.

### Use Cases

- Large document processing
- Video analysis
- Large image inference

### AWS Service

- SageMaker Asynchronous Endpoint

### Advantages

- Handles large payloads
- Cost efficient

---

## Serverless Inference

### Description

AWS automatically provisions compute resources.

### Use Cases

- Unpredictable traffic
- Low-volume workloads

### AWS Service

- SageMaker Serverless Endpoint

### Advantages

- Pay per request
- No infrastructure management

### Disadvantages

- Cold starts

### Exam Tip

If traffic is infrequent and unpredictable, choose Serverless Inference.

---

# Endpoint Comparison

| Requirement | Best Option |
|------------|-------------|
| Immediate response | Real-Time Endpoint |
| Large datasets | Batch Transform |
| Long-running inference | Asynchronous Endpoint |
| Sporadic traffic | Serverless Endpoint |

---

# Compute Selection

## CPU Instances

### Best For

- Traditional ML
- XGBoost
- Linear Models

### Examples

- m5
- c5

---

## GPU Instances

### Best For

- Deep Learning
- NLP
- Computer Vision
- Foundation Models

### Examples

- g5
- p4
- p5

### Exam Tip

Deep learning training generally requires GPUs.

---

# SageMaker Hosting Options

## Single-Model Endpoint

### Characteristics

- One model per endpoint

### Advantages

- Simplicity

### Disadvantages

- Higher cost

---

## Multi-Model Endpoint

### Characteristics

Multiple models hosted on one endpoint.

### Advantages

- Lower cost
- Better resource utilization

### Best Use Cases

- Many small models

### Exam Tip

If multiple models are rarely used, choose Multi-Model Endpoint.

---

## Multi-Container Endpoint

### Characteristics

Multiple containers hosted on a single endpoint.

### Benefits

- Different frameworks
- Shared infrastructure

---

# Container Types

## AWS Managed Containers

### Benefits

- Easy deployment
- Fully supported

### Examples

- TensorFlow
- PyTorch
- XGBoost

---

## Bring Your Own Container (BYOC)

### Benefits

- Full customization

### Use Cases

- Custom dependencies
- Specialized frameworks

### AWS Service

- Amazon ECR
- SageMaker

---

# SageMaker Neo

## Purpose

Optimize models for edge devices.

### Benefits

- Smaller models
- Faster inference

### Use Cases

- IoT
- Mobile devices
- Edge AI

### Exam Tip

Need edge optimization?
Choose SageMaker Neo.

---

# Deployment Targets

## SageMaker Endpoints

### Best For

Managed ML deployment.

---

## AWS Lambda

### Best For

Lightweight inference.

### Advantages

- Serverless
- Cost effective

---

## Amazon ECS

### Best For

Containerized applications.

---

## Amazon EKS

### Best For

Kubernetes-based deployments.

---

# Deployment Strategies

## Blue/Green Deployment

### Description

Deploy new version alongside existing version.

### Benefits

- Easy rollback
- Reduced risk

### Frequently Tested

Yes

---

## Canary Deployment

### Description

Deploy to small percentage of users first.

### Benefits

- Lower risk
- Gradual rollout

---

## Linear Deployment

### Description

Traffic shifts gradually.

### Benefits

- Controlled rollout

---

# Task 3.2: Create and Script Infrastructure

---

# Infrastructure as Code (IaC)

## Purpose

Automate infrastructure creation.

Benefits:

- Repeatability
- Version Control
- Automation

---

# AWS CloudFormation

## Description

Declarative infrastructure provisioning.

### Uses

- Create VPCs
- Deploy SageMaker resources
- Create EC2 instances

### Benefits

- Consistent deployments

---

# AWS CDK

## Description

Infrastructure defined using programming languages.

### Supported Languages

- Python
- TypeScript
- Java
- C#

### Benefits

- Reusable code
- Easier maintenance

### Exam Tip

CloudFormation = YAML/JSON

CDK = Programming Language

---

# On-Demand vs Provisioned Resources

## On-Demand

### Characteristics

Pay only when used.

### Advantages

- Flexible

### Disadvantages

- Higher cost

---

## Provisioned

### Characteristics

Reserved capacity.

### Advantages

- Predictable performance

### Disadvantages

- Potential over-provisioning

---

# Auto Scaling

## Purpose

Automatically adjust resources based on demand.

### Benefits

- Cost optimization
- High availability

---

# SageMaker Endpoint Auto Scaling

## Metrics

### Invocations Per Instance

Most commonly used.

---

### CPU Utilization

Scale based on CPU usage.

---

### Model Latency

Scale when latency increases.

### Exam Tip

Latency-based scaling is common for inference endpoints.

---

# Amazon ECR

## Purpose

Container image repository.

### Benefits

- Secure image storage
- Integration with ECS/EKS/SageMaker

---

# Amazon ECS

## Purpose

Managed container orchestration.

### Best For

- Simpler container management

---

# Amazon EKS

## Purpose

Managed Kubernetes.

### Best For

- Kubernetes workloads

---

# VPC Integration

## Purpose

Secure SageMaker resources.

### Components

- VPC
- Subnets
- Security Groups

### Benefits

- Private communication
- Compliance

### Exam Tip

Highly regulated workloads often require SageMaker inside a VPC.

---

# Spot Instances

## Purpose

Use spare AWS capacity.

### Advantages

- Up to 90% cheaper

### Disadvantages

- Can be interrupted

### Best Use Cases

- Training jobs
- Non-critical workloads

---

# Task 3.3: Use Automated Orchestration Tools to Set Up CI/CD Pipelines

---

# CI/CD Overview

## Continuous Integration (CI)

Automatically:

- Build code
- Run tests
- Validate changes

---

## Continuous Delivery (CD)

Automatically:

- Deploy applications
- Deploy models

---

# AWS CodeCommit

## Purpose

Git repository service.

### Uses

- Source control
- Collaboration

---

# AWS CodeBuild

## Purpose

Build and test applications.

### Responsibilities

- Compile code
- Execute tests

### Exam Tip

Build failures → investigate CodeBuild.

---

# AWS CodeDeploy

## Purpose

Deploy applications.

### Supports

- Blue/Green Deployment
- Canary Deployment

---

# AWS CodePipeline

## Purpose

Orchestrate CI/CD workflows.

### Stages

1. Source
2. Build
3. Test
4. Deploy

### Exam Tip

Need full automation pipeline?
Choose CodePipeline.

---

# Git Workflow Concepts

## GitFlow

### Branches

- Main
- Develop
- Feature
- Release
- Hotfix

### Best For

Large teams

---

## GitHub Flow

### Simpler Workflow

Feature Branch → Pull Request → Main

### Best For

Smaller teams

---

# SageMaker Pipelines

## Purpose

End-to-end ML workflow orchestration.

### Supports

- Data Processing
- Feature Engineering
- Training
- Evaluation
- Deployment

### Benefits

- Reproducibility
- Automation

### Frequently Tested

Yes

---

# Apache Airflow

## AWS Service

Amazon MWAA

(Managed Workflows for Apache Airflow)

### Purpose

Workflow scheduling and orchestration.

### Use Cases

- Data pipelines
- ML pipelines

---

# Event-Driven Automation

## Amazon EventBridge

### Purpose

Trigger actions automatically.

### Examples

- Start retraining
- Launch pipeline
- Run inference jobs

---

# Automated Retraining

## Common Trigger Sources

### EventBridge

Trigger retraining when:

- New data arrives
- Performance degrades

---

### SageMaker Pipelines

Automate:

- Training
- Evaluation
- Deployment

---

# Testing in ML CI/CD

## Unit Testing

Tests individual functions.

---

## Integration Testing

Tests component interactions.

---

## End-to-End Testing

Tests complete workflow.

### Exam Tip

Production ML systems should include all three.

---

# SageMaker SDK

## Purpose

Programmatically create:

- Training Jobs
- Endpoints
- Pipelines
- Batch Jobs

### Benefits

- Automation
- Repeatability

---

# Domain 3 Quick Revision

Remember:

- Real-Time Endpoint → Immediate predictions
- Batch Transform → Large offline datasets
- Async Endpoint → Long-running inference
- Serverless Endpoint → Unpredictable traffic
- Neo → Edge optimization
- ECR → Container registry
- ECS → Container orchestration
- EKS → Kubernetes
- CloudFormation → Infrastructure as Code
- CDK → Infrastructure using programming languages
- Auto Scaling → Cost + Performance optimization
- Spot Instances → Cheapest training option
- CodeBuild → Build and Test
- CodeDeploy → Deploy
- CodePipeline → Orchestrate CI/CD
- SageMaker Pipelines → ML workflow automation
- EventBridge → Event-driven retraining
- Blue/Green → Safest deployment strategy
- Canary → Gradual rollout