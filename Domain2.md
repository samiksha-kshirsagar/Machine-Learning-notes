# Domain 2: ML Model Development (26%)

---

# Task 2.1: Choose a Modeling Approach

## Overview

The goal of model selection is to choose the most appropriate machine learning algorithm, foundation model, or AWS AI service based on the business problem, data availability, interpretability requirements, cost, and performance.

---

# Machine Learning Problem Types

## Classification

### Definition
Predicts discrete categories or labels.

### Examples
- Spam detection
- Fraud detection
- Disease prediction
- Customer churn prediction

### Common Algorithms
- Logistic Regression
- Decision Trees
- Random Forest
- XGBoost
- Neural Networks

### Evaluation Metrics
- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC

---

## Regression

### Definition
Predicts continuous numerical values.

### Examples
- House price prediction
- Sales forecasting
- Temperature prediction

### Common Algorithms
- Linear Regression
- Random Forest Regressor
- XGBoost Regressor

### Evaluation Metrics
- RMSE
- MAE
- MSE
- R² Score

---

## Clustering

### Definition
Groups similar data points without labels.

### Examples
- Customer segmentation
- Market basket analysis

### Common Algorithms
- K-Means
- Hierarchical Clustering
- DBSCAN

---

## Recommendation Systems

### Examples
- Netflix recommendations
- Amazon product recommendations

### AWS Service
- Amazon Personalize

---

## Natural Language Processing (NLP)

### Examples
- Chatbots
- Sentiment Analysis
- Text Classification

### AWS Services
- Amazon Comprehend
- Amazon Translate
- Amazon Bedrock

---

## Computer Vision

### Examples
- Object Detection
- Face Recognition
- OCR

### AWS Services
- Amazon Rekognition
- Amazon Textract

---

# Selecting the Right Model

## Factors to Consider

### Data Size

Small Dataset:
- Logistic Regression
- Decision Trees

Large Dataset:
- XGBoost
- Neural Networks

---

### Interpretability

High Interpretability Needed:
- Linear Regression
- Logistic Regression
- Decision Trees

Low Interpretability Acceptable:
- Deep Learning
- Ensemble Models

---

### Cost

Low Cost:
- Built-in Algorithms
- Pretrained Models

Higher Cost:
- Large Foundation Models
- Deep Neural Networks

---

# AWS AI Services vs Custom Models

## When to Use AWS AI Services

Use when:
- Problem is common
- No custom training required
- Fast deployment needed

Examples:

| Business Need | AWS Service |
|--------------|-------------|
| Translation | Amazon Translate |
| Speech-to-Text | Amazon Transcribe |
| Image Analysis | Amazon Rekognition |
| Chatbot | Amazon Lex |
| OCR | Amazon Textract |
| Search | Amazon Kendra |

### Exam Tip
If AWS AI service already solves the problem, prefer it over building a custom ML model.

---

# SageMaker Built-In Algorithms

## XGBoost

### Best For
- Classification
- Regression

### Advantages
- High accuracy
- Handles missing values

### Frequently Tested
Yes

---

## Linear Learner

### Best For
- Classification
- Regression

### Advantages
- Fast training
- Interpretable

---

## K-Means

### Best For
- Clustering

---

## PCA (Principal Component Analysis)

### Purpose
Dimensionality reduction.

### Benefits
- Faster training
- Less storage
- Reduced overfitting

---

## BlazingText

### Purpose
Word embeddings and text classification.

---

## DeepAR

### Purpose
Time-series forecasting.

---

# SageMaker JumpStart

## Purpose

Provides:
- Foundation Models
- Pretrained Models
- Solution Templates

### Benefits

- Faster deployment
- Reduced development effort

### Exam Tip

If the question asks for the fastest way to deploy a pretrained model, choose SageMaker JumpStart.

---

# Amazon Bedrock

## Purpose

Provides access to foundation models through APIs.

### Supported Tasks

- Text Generation
- Chatbots
- Summarization
- Question Answering
- Content Creation

### Advantages

- No infrastructure management
- Serverless
- Managed foundation models

### Exam Tip

If generative AI is required, Bedrock is usually the correct answer.

---

# Task 2.2: Train and Refine Models

---

# Training Fundamentals

## Epoch

### Definition

One complete pass through the entire training dataset.

### Example

Dataset = 10,000 records

Epoch = Model sees all 10,000 records once.

---

## Batch Size

### Definition

Number of samples processed before updating model weights.

### Example

Batch Size = 32

Model processes 32 records at a time.

---

## Steps (Iterations)

### Definition

Number of parameter updates during training.

Formula:

Steps = Dataset Size / Batch Size

---

# Hyperparameters

## Definition

Settings configured before training begins.

Examples:

- Learning Rate
- Batch Size
- Epochs
- Number of Trees
- Number of Layers

---

# Hyperparameter Effects

| Hyperparameter | Effect |
|---------------|---------|
| Learning Rate | Controls update speed |
| Batch Size | Impacts memory and convergence |
| Epochs | Training duration |
| Number of Trees | Random Forest complexity |
| Layers | Neural Network complexity |

---

# Hyperparameter Tuning

## Grid Search

### Approach

Tests all combinations.

### Advantages

- Thorough

### Disadvantages

- Expensive

---

## Random Search

### Approach

Tests random combinations.

### Advantages

- Faster

### Disadvantages

- May miss best combination

---

## Bayesian Optimization

### Approach

Uses previous results to guide search.

### Advantages

- Most efficient

### AWS Service

SageMaker Automatic Model Tuning

### Exam Tip

SageMaker AMT uses Bayesian Optimization.

---

# SageMaker Automatic Model Tuning (AMT)

## Purpose

Automatically finds optimal hyperparameters.

### Benefits

- Better accuracy
- Reduced manual effort

---

# Overfitting

## Definition

Model memorizes training data and performs poorly on unseen data.

### Symptoms

Training Accuracy:
95%

Validation Accuracy:
70%

---

## Solutions

- More data
- Dropout
- Regularization
- Feature selection
- Early stopping

---

# Underfitting

## Definition

Model cannot learn patterns from data.

### Symptoms

Training Accuracy:
Low

Validation Accuracy:
Low

---

## Solutions

- Increase model complexity
- More features
- Train longer

---

# Regularization

## Purpose

Reduces overfitting.

---

## L1 Regularization

### Effect

Removes unimportant features.

### Also Called

Lasso Regression

---

## L2 Regularization

### Effect

Reduces weight magnitudes.

### Also Called

Ridge Regression

---

## Dropout

### Purpose

Randomly removes neurons during training.

### Benefits

Reduces overfitting.

---

# Early Stopping

## Purpose

Stops training when validation performance stops improving.

### Benefits

- Faster training
- Prevents overfitting

---

# Ensemble Methods

## Bagging

### Example

Random Forest

### Benefits

Reduces variance.

---

## Boosting

### Example

XGBoost

### Benefits

Improves weak learners.

---

## Stacking

### Definition

Combines multiple models using a meta-model.

---

# Transfer Learning

## Definition

Fine-tuning pretrained models on custom data.

### Examples

- Bedrock
- JumpStart models

### Benefits

- Faster training
- Less data required

---

# Distributed Training

## Purpose

Train across multiple machines.

### Benefits

- Reduced training time
- Larger datasets

---

# Model Compression

## Purpose

Reduce model size.

---

## Techniques

### Pruning

Removes unnecessary weights.

### Quantization

Uses lower precision numbers.

### Feature Reduction

Uses fewer features.

---

# SageMaker Model Registry

## Purpose

Stores and manages model versions.

### Benefits

- Version tracking
- Governance
- Auditing

### Exam Tip

If version control is required, use SageMaker Model Registry.

---

# Task 2.3: Analyze Model Performance

---

# Confusion Matrix

| | Predicted Positive | Predicted Negative |
|---|---|---|
| Actual Positive | TP | FN |
| Actual Negative | FP | TN |

---

# Accuracy

Formula:

Accuracy = (TP + TN) / Total

### Best When

Balanced datasets.

---

# Precision

Formula:

Precision = TP / (TP + FP)

### Focus

False Positives

### Example

Spam Detection

---

# Recall

Formula:

Recall = TP / (TP + FN)

### Focus

False Negatives

### Example

Disease Detection

### Exam Tip

If missing positive cases is costly, prioritize Recall.

---

# F1 Score

Formula:

F1 = 2 × (Precision × Recall) / (Precision + Recall)

### Best For

Imbalanced datasets

---

# RMSE

Root Mean Square Error

### Used For

Regression problems.

### Lower is Better

Yes

---

# ROC Curve

Shows:

True Positive Rate vs False Positive Rate

---

# AUC

Area Under ROC Curve

### Range

0 → 1

### Higher is Better

Yes

---

# Model Bias Detection

## SageMaker Clarify

### Capabilities

- Bias Detection
- Feature Attribution
- Explainability

### Exam Tip

Need model explainability?
Use SageMaker Clarify.

---

# Shadow Testing

## Purpose

Compare a new model against production without affecting users.

### Benefits

- Safe testing
- Performance validation

---

# SageMaker Debugger

## Purpose

Monitor training jobs.

### Detects

- Overfitting
- Vanishing gradients
- Convergence issues

### Exam Tip

Debug convergence problems → SageMaker Debugger.

---

# Reproducible Experiments

## SageMaker Experiments

Purpose:
Track training runs.

Stores:
- Hyperparameters
- Metrics
- Artifacts

---

# Domain 2 Quick Revision

Remember:

- Classification → Predict categories
- Regression → Predict numbers
- Clustering → Group data
- Bedrock → Generative AI
- JumpStart → Pretrained models
- AMT → Bayesian Optimization
- Overfitting → High train, low validation performance
- Dropout → Reduce overfitting
- Early Stopping → Stop unnecessary training
- Clarify → Bias + Explainability
- Debugger → Training issues
- Model Registry → Version control
- XGBoost → Most commonly tested algorithm
- Recall important for medical diagnosis
- F1 Score useful for imbalanced datasets